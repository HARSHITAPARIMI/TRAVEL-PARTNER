<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Travel App</title>
    <style>
        /* Add your CSS styles here */
    </style>
</head>
<body>
    <h1>Travel App</h1>
    <input type="text" id="searchInput" placeholder="Search for a destination">
    <button onclick="searchDestination()">Search</button>
    <div id="destinationInfo"></div>

    <script>
        // Sample destination data (you can replace this with real data)
        const destinations = [
            {
                name: "Paris",
                description: "The City of Light",
                image: "paris.jpg",
            },
            {
                name: "New York City",
                description: "The Big Apple",
                image: "nyc.jpg",
            },
            {
                name: "Tokyo",
                description: "The Capital of Japan",
                image: "tokyo.jpg",
            },
        ];

        function searchDestination() {
            const searchInput = document.getElementById("searchInput").value.toLowerCase();
            const destinationInfo = document.getElementById("destinationInfo");

            // Find the destination that matches the search input
            const destination = destinations.find(dest => dest.name.toLowerCase() === searchInput);

            if (destination) {
                // Display destination information
                destinationInfo.innerHTML = `
                    <h2>${destination.name}</h2>
                    <p>${destination.description}</p>
                    <img src="${destination.image}" alt="${destination.name}" width="300">
                `;
            } else {
                // Display a message if the destination is not found
                destinationInfo.innerHTML = "Destination not found.";
            }
        }
    </script>
</body>
</html>
