<h1>Chord Progression Generator</h1>
<label for="key-select">Choose a key:</label>
<select id="key-select">
    <option value="C">C</option>
    <option value="C#">C# / Db</option>
    <option value="Db">Db</option>
    <option value="D">D</option>
    <option value="D#">D# / Eb</option>
    <option value="Eb">Eb</option>
    <option value="E">E</option>
    <option value="F">F</option>
    <option value="F#">F# / Gb</option>
    <option value="Gb">Gb</option>
    <option value="G">G</option>
    <option value="G#">G# / Ab</option>
    <option value="Ab">Ab</option>
    <option value="A">A</option>
    <option value="A#">A# / Bb</option>
    <option value="Bb">Bb</option>
    <option value="B">B</option>
</select>

<label for="tonality-select">Choose a tonality:</label>
<select id="tonality-select">
    <option value="major">Major</option>
    <option value="minor">Minor</option>
</select>

<button id="generate-button">Generate Chord Progression</button>

<div id="progression-display"></div>

<script src="./script.js"></script>
