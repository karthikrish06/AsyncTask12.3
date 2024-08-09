// Function to fetch data using Promises
function fetchData(url) {
    return new Promise((resolve, reject) => {
        fetch(url)
            .then(response => response.json())
            .then(data => resolve(data))
            .catch(error => reject(error));
    });
}

// URL of the API (Replace with the actual API endpoint)
const apiUrl = 'https://jsonplaceholder.typicode.com/posts';

// Fetch data and display on the webpage
fetchData(apiUrl)
    .then(data => {
        const apiDataContainer = document.getElementById('apiData');
        // Display data as needed
        apiDataContainer.innerHTML = JSON.stringify(data, null, 2);
    })
    .catch(error => {
        console.error('Error fetching data:', error);
    }
);