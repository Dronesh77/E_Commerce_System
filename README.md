# E-commerce Recommendation System
## Overview
This project is an e-commerce platform with a personalized product recommendation system. The application uses content-based filtering to suggest products to users based on their search queries and interests.

## Features
- Content-based product recommendations
- User authentication (sign-up and sign-in)
- Trending products display
- Responsive design using Bootstrap
- Theme customization (default, dark, green)
- Display zoom functionality

## Tech Stack

- Frontend: HTML, CSS, JavaScript, Bootstrap 4
- Backend: Flask (Python)
- Database: MySQL
- Machine Learning: scikit-learn for TF-IDF vectorization and cosine similarity calculation

### Prerequisites

- Python 3.7+
- MySQL
- Required Python packages (listed in requirements.txt)

## Installation

1. Clone the repository:

`git clone <repository-url>`
`cd ecommerce-recommendation-system`


2. Create and activate a virtual environment (optional but recommended):

`python -m venv venv`

`source venv/bin/activate  # On Windows: venv\Scripts\activate`

3. Install dependencies:

`pip install -r requirements.txt`

4. Set up the MySQL database:

- Create a database named 'ecom'
- Update the database connection string in `app.py` if necessary:

`app.config['SQLALCHEMY_DATABASE_URI'] = "mysql://root:2906@127.0.0.1:3306/ecom"`

5. Initialize the database tables:

- Add these lines to app.py before the if name == 'main' block:

`with app.app_context():
    db.create_all()
`

6. Update file paths:

- Modify the file paths in app.py to match your dataset locations:

`trending_products = pd.read_csv("/path/to/your/trending_products.csv")`
`train_data = pd.read_csv("/path/to/your/clean_data.csv")`


## Running the Application

1. Run the Flask application:

`python app.py`

2. Open your web browser and navigate to:

`http://127.0.0.1:5000/`


## Project Structure

`app.py`: Main Flask application file
`templates/`: HTML templates

`index.html`: Landing page with trending products
`main.html`: Main page with search functionality


`static/`: Static files (images, CSS, JavaScript)

## How the Recommendation System Works
The recommendation system uses content-based filtering with the following approach:

1. TF-IDF vectorization is applied to product tags/descriptions
2. Cosine similarity is calculated between the query product and all other products
3. Products with the highest similarity scores are recommended to the user

## Future Improvements

- Implement collaborative filtering
- Add user browsing history for better recommendations
- Integrate product categories and filters
- Add a shopping cart functionality
- Implement session management
- Enhance UI/UX design

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.