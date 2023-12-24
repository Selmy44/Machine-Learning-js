<!DOCTYPE html>
<html>
<head>
    <title>Machine Learning Web App</title>
    <!-- You may include CSS for styling -->
    <style>
        /* Your CSS styles go here */
    </style>
</head>
<body>
    <h1>Machine Learning Web App</h1>
    <div>
        <label for="inputData">Enter Data:</label>
        <input type="text" id="inputData">
        <button onclick="predict()">Predict</button>
    </div>
    <div id="predictionResult">
        <!-- Display prediction result here -->
    </div>

    <script>
        // Function to perform prediction
        function predict() {
            // Get input data from the user
            const inputData = document.getElementById('inputData').value;

            // Make an API call to the back-end for prediction using the input data
            // This part would typically involve using fetch() or XMLHttpRequest to communicate with the server where your model is hosted

            // For example:
            fetch('/predict', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify({ data: inputData }),
            })
            .then(response => response.json())
            .then(data => {
                // Display the prediction result to the user
                const predictionResult = document.getElementById('predictionResult');
                predictionResult.innerHTML = `<p>Prediction: ${data.prediction}</p>`;
            })
            .catch(error => {
                console.error('Error:', error);
            });
        }
    </script>
</body>
</html>
