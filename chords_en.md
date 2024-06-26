---
layout: chord
lang: EN
ref: chords
category: Chords
---

<h1>Chord progression generator</h1>
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
<button onclick="generateProgressions()">Generate progressions</button>
<div id="output"></div>

