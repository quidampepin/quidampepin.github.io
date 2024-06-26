---
layout: page
lang: EN
ref: chords
category: Chords
---
 <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            line-height: 1.6;
        }
        h1 {
            color: #333;
        }
        #output {
            margin-top: 20px;
            border: 1px solid #ddd;
            padding: 10px;
            background-color: #f9f9f9;
        }
        select, button {
            margin: 10px 0;
            padding: 5px;
        }
    </style>    
<body>
    <h1>Chord Progression Generator</h1>
    <label for="key">Select the key: </label>
    <select id="key" name="key">
        <option value="C">C</option>
        <option value="C#">C#</option>
        <option value="D">D</option>
        <option value="D#">D#</option>
        <option value="E">E</option>
        <option value="F">F</option>
        <option value="F#">F#</option>
        <option value="G">G</option>
        <option value="G#">G#</option>
        <option value="A">A</option>
        <option value="A#">A#</option>
        <option value="B">B</option>
    </select>
    <br>
    <label for="scale">Select the scale: </label>
    <select id="scale" name="scale">
        <option value="major">Major</option>
        <option value="minor">Minor</option>
    </select>
    <br>
    <button onclick="generateProgressions()">Generate Progressions</button>
    <div id="output"></div>
    <script>
        const majorScale = ["I", "ii", "iii", "IV", "V", "vi", "vii°"];
        const minorScale = ["i", "ii°", "III", "iv", "v", "VI", "VII"];

        const majorProgressions = [
    ["I", "V", "vi", "IV"],
    ["I", "IV", "V"],
    ["ii", "V", "I"],
    ["I", "vi", "IV", "V"],
    ["I", "V", "vi", "iii", "IV", "I", "IV", "V"],
    ["I", "IV", "vi", "V"],
    ["I", "V", "vi", "IV", "I", "V", "IV", "V"],
    ["I", "iii", "IV", "vi"],
    ["I", "vi", "ii", "V"],
    ["I", "IV", "I", "V"],
    ["I", "V", "IV", "V"],
    ["ii", "IV", "V", "I"],
    ["I", "V", "vi", "iii", "IV", "I", "ii", "V"],
    ["I", "iii", "vi", "IV"],
    ["I", "V", "IV", "I"],
    ["I", "IV", "ii", "V"],
    ["I", "vi", "iii", "V"],
    ["I", "IV", "V", "vi"],
    ["I", "V", "ii", "IV"],
    ["I", "iii", "IV", "V"],
    ["I", "vi", "IV", "ii", "V"],
    ["I", "IV", "I", "V", "vi", "IV", "ii", "V"],
    ["I", "V", "vi", "IV", "ii", "V", "I"],
    ["I", "iii", "vi", "ii", "V"],
    ["I", "IV", "V", "iii", "vi"],
    ["IV", "V", "I", "vi"],
    ["vi", "IV", "I", "V"],
    ["V", "vi", "IV", "I"],
    ["iii", "IV", "I", "V"],
    ["IV", "I", "V", "vi"],
    ["V", "IV", "I"],
    ["ii", "IV", "I", "V"]
];

const minorProgressions = [
    ["i", "iv", "v"],
    ["i", "VI", "III", "VII"],
    ["i", "iv", "VII", "III"],
    ["i", "v", "VI", "v"],
    ["i", "VII", "VI", "VII"],
    ["i", "VI", "VII", "v"],
    ["i", "iv", "VII", "v"],
    ["i", "III", "VII", "iv"],
    ["i", "v", "iv", "i"],
    ["i", "VI", "III", "iv"],
    ["i", "iv", "v", "i"],
    ["i", "VII", "VI", "v"],
    ["i", "ii°", "v", "i"],
    ["i", "iv", "III", "VII"],
    ["i", "VI", "iv", "v"],
    ["i", "v", "VI", "III"],
    ["i", "iv", "i", "v"],
    ["i", "VII", "III", "VI"],
    ["i", "III", "iv", "v"],
    ["i", "ii°", "V", "i"],
    ["i", "iv", "VII", "VI"],
    ["i", "v", "iv", "v"],
    ["i", "VI", "iv", "III", "VII"],
    ["i", "iv", "v", "VI", "III", "VII"],
    ["i", "III", "VI", "iv", "v", "i"],
    ["iv", "i", "v", "VI"],
    ["VI", "VII", "i", "iv"],
    ["v", "i", "iv", "VII"],
    ["iv", "VII", "i", "III"],
    ["ii°", "V", "i"],
    ["VII", "i", "VI", "v"],
    ["III", "iv", "i", "v"],
    ["iv", "i", "VII", "III"],
    ["VII", "iv", "i", "v"],
    ["VI", "ii°", "i", "v"]
];

        const keyMap = {
            "C": ["C", "D", "E", "F", "G", "A", "B"],
            "C#": ["C#", "D#", "E#", "F#", "G#", "A#", "B#"],
            "D": ["D", "E", "F#", "G", "A", "B", "C#"],
            "D#": ["D#", "E#", "F##", "G#", "A#", "B#", "C##"],
            "E": ["E", "F#", "G#", "A", "B", "C#", "D#"],
            "F": ["F", "G", "A", "Bb", "C", "D", "E"],
            "F#": ["F#", "G#", "A#", "B", "C#", "D#", "E#"],
            "G": ["G", "A", "B", "C", "D", "E", "F#"],
            "G#": ["G#", "A#", "B#", "C#", "D#", "E#", "F##"],
            "A": ["A", "B", "C#", "D", "E", "F#", "G#"],
            "A#": ["A#", "B#", "C##", "D#", "E#", "F##", "G##"],
            "B": ["B", "C#", "D#", "E", "F#", "G#", "A#"],
            "C minor": ["C", "D", "Eb", "F", "G", "Ab", "Bb"],
            "C# minor": ["C#", "D#", "E", "F#", "G#", "A", "B"],
            "D minor": ["D", "E", "F", "G", "A", "Bb", "C"],
            "D# minor": ["D#", "E#", "F#", "G#", "A#", "B", "C#"],
            "E minor": ["E", "F#", "G", "A", "B", "C", "D"],
            "F minor": ["F", "G", "Ab", "Bb", "C", "Db", "Eb"],
            "F# minor": ["F#", "G#", "A", "B", "C#", "D", "E"],
            "G minor": ["G", "A", "Bb", "C", "D", "Eb", "F"],
            "G# minor": ["G#", "A#", "B", "C#", "D#", "E", "F#"],
            "A minor": ["A", "B", "C", "D", "E", "F", "G"],
            "A# minor": ["A#", "B#", "C#", "D#", "E#", "F#", "G#"],
            "B minor": ["B", "C#", "D", "E", "F#", "G", "A"]
        };

        function getChordName(scale, index, chord, isMinorKey) {
            let note = scale[index];
            if (isMinorKey) {
                if (["i", "iv", "v"].includes(chord)) {
                    note += "m";
                } else if (chord === "ii°") {
                    note += "dim";
                } else if (chord === "V") {
                    note += "M";
                }
            } else {
                if (["ii", "iii", "vi"].includes(chord)) {
                    note += "m";
                } else if (chord === "vii°") {
                    note += "dim";
                }
            }
            return note;
        }

        function getChordIndex(scale, chord) {
            if (chord === "V" && scale === minorScale) {
                return 4;
            }
            return scale.indexOf(chord);
        }

        function getProgressions(key, scaleType) {
            const isMinorKey = scaleType === "minor";
            const scale = isMinorKey ? minorScale : majorScale;
            const progressions = isMinorKey ? minorProgressions : majorProgressions;
            const selectedProgressions = progressions.sort(() => 0.5 - Math.random()).slice(0, 3);

            const keyNotes = keyMap[key];
            return selectedProgressions.map(progression => {
                const translatedProgression = progression.map(chord => {
                    const index = getChordIndex(scale, chord);
                    return getChordName(keyNotes, index, chord, isMinorKey);
                });
                return [progression, translatedProgression];
            });
        }

        function generateProgressions() {
            const key = document.getElementById('key').value;
            const scaleType = document.getElementById('scale').value;

            const progressions = getProgressions(key, scaleType);
            
            let output = '';
            progressions.forEach(([numeral, chords]) => {
                output += `Numeral Notation: ${numeral.join(' - ')}<br>`;
                output += `Chord Progression in Key: ${chords.join(' - ')}<br><br>`;
            });

            document.getElementById('output').innerHTML = output;
        }
    </script>
</body>