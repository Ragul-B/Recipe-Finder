# <span id="project-title"></span>

This project is a real-time recipe finder application that allows users to search for recipes based on ingredients or dish names.

## Features

- **Search Recipes**: Enter ingredients or dish names to find relevant recipes.
- **Dynamic Results**: Results update instantly as you type or submit the search.
- **View Details**: Click on recipes to view detailed ingredients and cooking instructions.
- **Responsive Design**: Optimized for various screen sizes to provide a seamless user experience.

## Getting Started

1. **Clone the Repository**

 <li><strong>Clone the Repository</strong></li>
    <pre>git clone https://github.com/your-username/recipe-finder.git
cd recipe-finder</pre>

2. **Set Up API Keys**

- Sign up for the Edamam Recipe API and obtain your Application ID and API Key.
- Update the `app.js` file with your API credentials:

  ```javascript
  const appId = 'YOUR_EDAMAM_APP_ID';
  const appKey = 'YOUR_EDAMAM_API_KEY';
  ```

3. **Run the Application**

Open `index.html` in your web browser or use a local server to view the application.

## Usage

- Enter ingredients or dish names in the search bar.
- Press Enter or click the search button to fetch recipes.
- Click on any recipe card to view detailed instructions and nutritional information.

## Contributing

Contributions are welcome! Feel free to open issues or pull requests to suggest improvements or report bugs.

## License

This project is licensed under the [MIT License](LICENSE).

<script>
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
#project-title {
 border-right: 2px solid #333;
 white-space: nowrap;
 overflow: hidden;
 animation: typing 3s steps(30, end);
}

@keyframes typing {
 from { width: 0 }
 to { width: 100% }
}
</style>
