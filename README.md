# SQLAlchemy Restaurant Review System

## Phase 3 Week 3 Code Challenge

## Overview

This system is a Restaurant Review application developed with Python, utilizing SQLAlchemy and Alembic Migrations, SQLAlchemy Relationships, Class and Instance Methods, and SQLAlchemy Querying. The application is tailored for a Yelp-style domain, comprising three core models: Restaurant, Review, and Customer.

---

## Table of Contents

- [Prerequisites](#prerequisites)
- [Features](#features)
- [Project Setup](#project-setup)
- [Entity Relationship Diagram](#entity-relationship-diagram)
- [Usage](#usage)
  - [Methods](#methods)
    - [Restaurant](#restaurant)
    - [Usage](#customer)
    - [Review](#review)
- [Author & License](#author--license)

---

## Prerequisites

The necessary packages are outlined in the Pipfile and can be installed into the virtual environment using:

- Python3 v3.10 +
- SQLAlchemy v2.0.20
- Alembic v1.12.0
- Faker v19.3.1

---

## Features

- Create and manage customer and restaurant profiles
- Add, retrieve, and delete reviews for restaurants
- Find customers and restaurants based on reviews
- Retrieve a list of all reviews
- Identify the fanciest restaurant in the list
- Discover a customer's favorite restaurant

---

## Project Setup

1. Navigate to the project's directory:

bash
cd sqlalchemy_restaurants


2. Install required dependencies:

bash
pipenv install


3. Activate the virtual environment:

bash
pipenv shell


4. Navigate into the app directory:

bash
cd app


5. Run main.py for testing:

bash
./main.py


---

## Usage

Utilize the Restaurant Review System to simulate interactions between customers, restaurants, and reviews to:

1. Create customer and restaurant instances.
2. Add reviews using the add_review method.
3. Retrieve information about customers, restaurants, and reviews using the provided methods.

For instance, you should be able to call session.query(Customer).first().all_restaurants() and view a list of restaurants for the first customer in the database based on your seed data. Similarly, session.query(Review).first().customer should return the customer for the first review in the database.

### Methods

Use the seed.py file to generate sample data for testing the models and relationships through the following methods.

#### Restaurant

*

self.all_reviews()

- changed from self.reviews() in deliverables

- returns a collection of all the reviews for the Restaurant

self.all_customers()

- changed from self.customers() in deliverables.

- returns a collection of all the customers who reviewed the Restaurant

cls.fanciest()

- A *class* method that returns **one** restaurant instance for the restaurant with the highest price

self.all_reviews_formatted()

- returns a list of strings with all the reviews for this restaurant in the following format:

python
[ "Review for {insert restaurant name} by {insert customer's full name}: {insert review star_rating} stars.",

"Review for {insert restaurant name} by {insert customer's full name}: {insert review star_rating} stars.", ]


#### Customer

*

self.all_reviews()

- changed from self.reviews() in deliverables.

- returns a collection of all the reviews that the Customer has left

self.all_restaurants()

changed from self.restaurants() in deliverables.

- returns a collection of all the restaurants that the Customer has reviewed

self.full_name()

- returns the full name of the customer, with the first name and the last name concatenated, Western style.

self.favorite_restaurant()

- returns the restaurant instance that has the highest star rating from this customer

self.add_review(restaurant, rating)

- takes a restaurant (an instance of the Restaurant class) and a rating

- creates a new review for the restaurant with the given restaurant_id

self.delete_reviews(restaurant)

- takes a restaurant (an instance of the Restaurant class) and

- removes *all* their reviews for this restaurant

#### Review

*

review.customer()

- returns the Customer instance for this review

review.restaurant()

- returns the Restaurant instance for this review

review.full_review()

- returns a string in the following format:

text
Review for {insert restaurant name} by {customer full_name}: {review star_rating} stars.


---

## Author & License

Author: matchy

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.
