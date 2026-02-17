# Use Case: How to Access DJ Mixes
This use case example demonstrates how to configure a third-party app to let users select a DJ and access a specific mix using the Ma Radio Groove API. 

!!! note
    In the following requests: all endpoint paths are appended to the base URL `https://api.maradiogroove.com/v1`, and all mentions of `YOUR_API_KEY` need to be replaced with the API key you generated.

<h2>Procedure</h2>
<ol>
<li>
Send the following request to retrieve the list of DJs:
<pre><code class="bash">curl -H "Authorization: Bearer YOUR_API_KEY" https://api.maradiogroove.com/v1/djs
</code></pre>

<strong>Example JSON response:</strong>
<pre><code class="json">{
  "data": [
    { "id": "dj_001", "name": "DJ Groove" },
    { "id": "dj_002", "name": "DJ Sunset" }
  ]
}
</code></pre>
</li>

<li>Choose a DJ from the list (e.g. <em>DJ Groove</em> with ID <code>dj_001</code>).</li>

<li>
Send the following request to retrieve the list of mixes for the selected DJ:
<pre><code class="bash">curl -H "Authorization: Bearer YOUR_API_KEY" https://api.maradiogroove.com/v1/djs/dj_001/mixes
</code></pre>

<strong>Example JSON response:</strong> 
<pre><code class="json">{
  "data": [
    { "id": "mix_101", "title": "Afro House Sunset", "duration": 3600 },
    { "id": "mix_103", "title": "Evening Chill", "duration": 3000 }
  ]
}
</code></pre>
</li>

<li>Choose a mix from the list (e.g. <em>Afro House Sunset</em> with ID <code>mix_101</code>).</li>

<li>
Send the following request to retrieve the details of the selected mix:
<pre><code class="bash">curl -H "Authorization: Bearer YOUR_API_KEY" https://api.maradiogroove.com/v1/mixes/mix_101
</code></pre>

<strong>Example JSON response:</strong>
<pre><code class="json">{
  "id": "mix_101",
  "title": "Afro House Sunset",
  "dj": { "id": "dj_001", "name": "DJ Groove" },
  "duration": 3600,
  "genre": "House",
  "description": "A smooth afro house mix perfect for evening private parties."
}
</code></pre>
</li>
</ol>

<h2>Result</h2>
<p>The selected mix is now ready for playback in the third-party app.</p>
