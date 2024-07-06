<!-- Typing Animation Script -->
<script>
  // Typing animation script
  const titleElement = document.querySelector('#project-title');

  const texts = ['Real-Time Recipe Finder', 'Search Recipes Instantly', 'Discover New Culinary Delights'];
  let index = 0;
  let charIndex = 0;
  let currentText = '';
  let isDeleting = false;

  function type() {
    if (charIndex < texts[index].length) {
      currentText += texts[index].charAt(charIndex);
      titleElement.innerHTML = currentText;
      charIndex++;
      setTimeout(type, 100);
    } else {
      setTimeout(erase, 1000);
    }
  }

  function erase() {
    if (charIndex > 0) {
      currentText = texts[index].substring(0, charIndex - 1);
      titleElement.innerHTML = currentText;
      charIndex--;
      setTimeout(erase, 50);
    } else {
      index++;
      if (index >= texts.length) index = 0;
      setTimeout(type, 1000);
    }
  }

  document.addEventListener('DOMContentLoaded', function() {
    setTimeout(type, 100);
  });
</script>

<style>
  body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    background-color: #f5f5f5;
    margin: 0;
    padding: 0;
  }

  .container {
    max-width: 800px;
    margin: 50px auto;
    padding: 20px;
    background-color: #fff;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
    border-radius: 8px;
  }

  h1, h2, h3, h4, h5 {
    color: #333;
  }

  p {
    color: #666;
  }

  code {
    background-color: #f0f0f0;
    padding: 0.2em 0.5em;
    border-radius: 4px;
    font-family: 'Courier New', Courier, monospace;
  }

  ul {
    list-style-type: disc;
    padding-left: 20px;
    color: #666;
  }

  pre {
    background-color: #f0f0f0;
    padding: 10px;
    border-radius: 8px;
    overflow-x: auto;
    font-family: 'Courier New', Courier, monospace;
  }
</style>

<div class="container">
  <h1><span id="project-title"></span></h1>

  <p>This project is a real-time recipe finder application that allows users to search for recipes based on ingredients or dish names. It utilizes the Edamam Recipe API to fetch real-time recipe data and display it dynamically on the web page.</p>

  <h2>Features</h2>
  <ul>
    <li><strong>Search Recipes:</strong> Enter ingredients or dish names to find relevant recipes.</li>
    <li><strong>Dynamic Results:</strong> Results update instantly as you type or submit the search.</li>
    <li><strong>View Details:</strong> Click on recipes to view detailed ingredients and cooking instructions.</li>
    <li><strong>Responsive Design:</strong> Optimized for various screen sizes to provide a seamless user experience.</li>
  </ul>

  <h2>Getting Started</h2>
  <ol>
    <li><strong>Clone the Repository</strong></li>
    <pre>git clone https://github.com/your-username/recipe-finder.git
cd recipe-finder</pre>

    <li><strong>Set Up API Keys</strong></li>
    <p>Sign up for the Edamam Recipe API and obtain your Application ID and API Key. Update the <code>app.js</code> file with your API credentials:</p>
    <pre><code>const appId = 'YOUR_EDAMAM_APP_ID';
const appKey = 'YOUR_EDAMAM_API_KEY';</code></pre>

    <li><strong>Run the Application</strong></li>
    <p>Open <code>index.html</code> in your web browser or use a local server to view the application.</p>
  </ol>

  <h2>Usage</h2>
  <p>Enter ingredients or dish names in the search bar. Press Enter or click the search button to fetch recipes. Click on any recipe card to view detailed instructions and nutritional information.</p>

  <h2>Contributing</h2>
  <p>Contributions are welcome! Feel free to open issues or pull requests to suggest improvements or report bugs.</p>

  <h2>License</h2>
  <p>This project is licensed under the <a href="LICENSE">MIT License</a>.</p>
</div>

<div class="container">
  <h2>Development</h2>
  <p>For developers looking to extend or modify the project:</p>
  <ul>
    <li>Ensure API credentials are kept secure and not exposed in public repositories.</li>
    <li>Implement additional features such as filtering by dietary preferences or saving favorite recipes.</li>
  </ul>

  <h2>Notes</h2>
  <p>Customize the content further based on specific functionalities or enhancements in your recipe finder application.</p>
</div>
