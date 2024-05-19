# AI Commerce Automation

Welcome to the AI Commerce Automation repository! 🚀

## About

AI Commerce Automation is a research based on various emerging technologies to revolutionize the way ecommerce businesses operate. By harnessing the power of artificial intelligence, this application automates various tasks, streamlines processes, and enhances the overall efficiency of your online store.

## Features

### Search By Image

Client-Side (JavaScript):

1. User Input: The user selects an image file from their device using an HTML file input element.
2. Image Processing: Once an image is selected, JavaScript reads the image file and converts it into a Base64 encoded string. Base64 encoding represents binary data (like images) as a text format suitable for sending it through an HTTP request. Since we cannot pass image to celery we use string representation of the file.
3. AJAX Request: The JavaScript code sends an AJAX request to a specific URL on the server, defined as `/search-by-image/`. This request carries the Base64 encoded image data in the request body.

Server-Side (Django):

1. Receive Image Data: The Django view function receives the AJAX request containing the Base64 encoded image data.
2. Process Image: Using the model hosted in the replicate computing platform the model extracts the caption using the trained model.
3. Search for Similar Products: The text data which is extracted using machine learning model is  used to search for products in our database that are visually similar.
4. Return Search Results: The view function sends a JSON response containing details of the matching products, including title, price, and potentially image URLs (if stored separately).

Client-Side (Response Handling):

1. Receive Response: The JavaScript code receives the JSON response from the server.
2. Parse Results: The response data is parsed to extract information about the matching products.
3. Display Results: The JavaScript dynamically generates HTML content displaying the retrieved products. This involves creating product cards with titles, images, and prices. If no matching products are found, an appropriate message is displayed.

Benefits:

- Simplified Product Search: Users can find similar products without manually entering text descriptions.
- Improved User Experience: Provides a more intuitive way to search for visual items.
- Accessibility: Can be helpful for users who have difficulty describing products in words.

## Getting Started

To use AI Commerce Automation, follow these simple steps:

1. **Clone the Repository:** Clone this repository to your local machine using `git clone https://github.com/isuru0x01/AI-Driven-Ecommerce.git`.

3. **Configure Settings:** Rename the sample.env to .env and add required APIs.

4. **Run the Application:** Start the application by running `docker compose up --build` and access it via your web browser.

5. **Explore and Customize:** Explore the features of AI Commerce Automation and customize them to suit your specific needs. Don't hesitate to experiment and innovate!

## Contributing

We welcome contributions from the community to enhance AI Commerce Automation further. Whether it's adding new features, fixing bugs, or improving documentation, your contributions are invaluable.

## Support

If you encounter any issues or have any questions, feel free to reach out to us or open an issue in the repository.

## License

This project is licensed under the [MIT License](LICENSE).

---