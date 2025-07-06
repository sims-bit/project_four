# Project Name

## Table of Contents
- Overview 
- User Experience (UX)
- Features
- Data Schema
- Technologies Used
- Testing
- Deployment
- Credits

1. Overview

## Project Purpose
This is an online fashion retail website specializing in women's clothing with a focus on a particular modern take on a cottagecore style. With the site featuring a curated collection of clothing and accessories.

With the fashion e-commerce space dominated by fast fashion retailers offering overwhelming product selections that often lack cohesion. There's a clear opportunity for a curated, quality-focused alternative.
The value the site provides to users is that it offers users a carefully curated selection of cohesive, clothing and accessory pieces, making outfit planning easier. Whilst delivering a seamless shopping experience with professional product photography.

<strong>Target audience</strong><br>
The ideal target audience for the site is individuals who value quality over fast fashion trends, those looking for coordinated wardrobe pieces that could also be utilized as individual statement items.

<strong>Real-world problem solving</strong><br>
With growing consumer awareness about sustainable fashion and quality clothing has created demand for retailers that prioritize curation over volume, justifying a premium positioning strategy. This site eliminates the overwhelming choice paralysis common in fast fashion retail, by paying concious effort to maintain a clear brand identity, this inturn provides an alternative to mass-market fashion and leaning away from being another fast fashion brand with all the environmental issues of mass production. Whilst maintaining consistant high quality.

2. User Experience (UX)

### Design Process

- The minimilst design interface prioritizes product visibility and easy navigation over flashy design elements, allowing the clothing to be the focal point and reducing visual clutter that can overwhelm users.
- A cohesive identity creates a strong reliable brand identity 
- Responsive design prioritizing mobile devices with adaptive templates
- Collapsible navigation menu optimized for mobile interfaces
- Intuitive, accessible interface designed for optimal readability and a streamlined shopping experience 
- User control features -- adding and subtacting to the bag, personal information, ability to create a user profile 
- Confirmation and feedback toasts for user feedback keep in line with the chosen aesthetics of the site


3. Features

    - Main navigation and structured layout     
    - User authentication (registration/login/logout)
    - Form validation and user feedback
    - E-commerce payment system integration using stripe
    - Error handling and user notifications
    - Responsive design implementation

### Future Features
- Future enhancements/ expansions of features may include the site branching out into childrens wear.
- Discount codes
- Delivery Tracking

### Apps Structure
<strong>My apps</strong>
- Home
- Products
- Bag
- Checkout
- Profiles 
<br>

4. Data Schema
<br>
<details>
    <summary>Entity Relationship Diagram (ERD)</summary>
    <br>
    <img src="/readme_media/weekend_erd-diagram.jpg" alt="">
    </details>

- Checkout - Order Model:
The core order management model that handles customer purchase transactions. Contains comprehensive customer information, delivery details, and order totals with payment processing fields.
- Checkout - OrderLineItem Model:
A junction model that represents individual products within an order, handling the many-to-many relationship between orders and products with additional context like quantity and totals.
- Profiles - User Profile Model:
An extended user profile model that stores default customer information for streamlined future purchases and account management.
- Products - Category Model:
A simple categorization model for organizing products with both internal and customer-friendly naming conventions.
- Products - Product Model:
The comprehensive product catalog model containing all product information including variants, pricing, descriptions, and media assets.

<strong>Data Validation</strong>

- Order number uniqueness: Prevents duplicate order numbers
- SKU uniqueness: Product SKU field likely enforces uniqueness for inventory management

- Email validation: Email field in Order model ensures proper email format
- Decimal precision: Financial fields (price, totals, costs) use decimal type for accurate caluculations
- Phone number validation: Phone number field validates proper formatting
- Date validation: Date fields ensure proper timestamp formatting

- Required fields: Essential fields like order_number, email, full_name are mandatory

- Order number uniqueness: Prevents duplicate order numbers
- SKU uniqueness: Product SKU field likely enforces uniqueness for inventory management

- User profile link: Order model validates user_profile exists if provided (for registered users)

- Data Validation/ Security with Stripe

### CRUD Operations
Site/Shop owner has CRUD functionality to create, view, edit and delete products for the site. 
The Site user/ client CRUD functionality is to add, edit and delete products from the bag.

5.  Technologies Used

### Languages
- Python
- HTML5
- CSS3
- JavaScript

### Frameworks and Libraries
- Django (version)
- Bootstrap

### Database
- Code Institute Postgres Database
- Amazon S3 cloud storage (for images)

### Payment Processing
- Stripe

### Other Tools
- Version control (Git)
- Development environment (Visual Studio Code)
- Deployment platform (Github and Heroku)

- JSHint
- Pylint
- Lighthouse
- Jason Formatter 
- W3schools  


### Requirements 
- boto3==1.38.46
- dj-database-url==0.5.0
- Django==3.2.25
- django-allauth==0.50.0
- django-countries==7.2.1
- django-crispy-forms==1.14.0
- django-storages==1.14.6
- gunicorn==23.0.0
- psycopg2==2.9.10
- stripe==12.2.0

5.  Testing

### Testing Strategy

| Test Category | Test Case | Test Description | Status |
|---  | --- | --- | --- |
|Home Page Functionality| | | |
|Navigation | Header Navigation  | All links functional, pages load correctly | PASS|
|Layout | Responsive Design | Layout adapts properly to screen sizes | PASS|
|Content | Hero Image Loading | All images load quickly and display properly |PASS|
|Navigation | Dropdown Menu | All menus dropdown and collapse as intended |PASS|
|Products | | |
|Product Navigation/ Sorting functionality | Prod |   |
|Product Display | Price Display | Prices display correctly in GDP |PASS|
|Product Display | Image Display | Images are high quality and load properly |PASS|
|Product Details | Individual Product Page | Product page loads with complete information |PASS |
|Product Options | Size Selection | Size options work correctly|PASS |
|Product Actions | Add to Cart | Product adds to bag successfully |PASS |
|Shopping bag | | | |
|Bag Managment |View Bag | Bag displays correct items and quantities |PASS |
|Bag Managment | Update Quantitites | Quantities of items and grand total of shopping bag are updated correctly |PASS |
|Bag Managment | Removing Items | Items remove successfully from bag |PASS |
|Bag Calculations | Subtotal calculation | Calculations are accurate |PASS |
|Checkout | | | |
|Checkout procedure | Checkout Flow | Checkout process flows smoothly |PASS |
|Form validation | Required Fields | Proper Validation and error message displays |PASS |
|Payment | Payment Methods | Payment Methods work and are secure |PASS |
|Search and Filtering | | | |
|Search | Site Search |Search returns relevant results |PASS |
|Filtering |Category Filtering |Filters work correctly and update results |PASS |


|Performace | | | |
|---  | --- | --- |
|Loading Speed |Page load times |Pages load within acceptable time |PASS |
|Responsivity | Responsivity| Teested on several screensizes through chrome developer tools| Pass |


<details>
    <summary>Lighthouse</summary>
    <br>
    <img src="/readme_media/initial_lighthouse_report.jpg" alt="">
    <img src="/readme_media/higher_lighthouse_report.jpg" alt="">
    </details>

### Responsive Testing
- Browsers: Chrome, Firefox, Safari, Edge
- Devices: Desktop, Tablet, Mobile

### Validation

<details>
    <summary>HTML validation (W3C)</summary>
    <br>
    <img src="/readme_media/html_validation.jpg">
    <img src="/readme_media/html_complete validation.jpg" alt="">
    <p>You are able to see that the warnings occur in the full validation from the joining of the</p>
    </details> HERE


<details>
    <summary>CSS validation (Jigsaw)</summary>
    <br>
    <img src="/readme_media/css_validation_fail.jpg" alt="">
    <img src="/readme_media/css_validation_pass.jpg" alt="">
    </details>


<details>
    <summary>JavaScript validation (JSHint)</summary>
    <br>
    <img src="/readme_media/jshint_stripe_validation.jpg" alt="">
    <img src="/readme_media/countryfield_jshint_validation.jpg" alt="">
    </details>


<details>
    <summary>Python code style (Pylint)</summary>
    <br>
    <img src="/readme_media/pylint_first_validation.jpg" alt="">
    <img src="/readme_media/pylint_validation_success.jpg" alt="">
    </details>


### Bug Fixes
- Known issues and their resolutions

BUGS
- The are no outstanding bugs to my knowledge

<br>
6.  Deployment

### Heroku Deployment Process

    Database Setup - Navigate to PostgreSQL from Code Institute - Enter in your student email address and click submit - Wait whilst your database is created - Your database is sucessfully created, you will receive an email with the database link

    Log into Heroku and create a new app with a unique name. This will be added to the allowed hosts in the project settings.

    Following on, within the setting tab of your app:

    Locate the 'Reveal Config Vars', in which we shall be adding a new Config Var called DISABLE_COLLECTSTATIC, assign it the value of 1 and then save it via clicking add. This will be removed when relasing for production.

    Add a new Config Var called SECRET_KEY and assign it a value - any random string of letters, digits and symbols. (You can use an online generator for this) Click add to save.

    Add a new Config Var called DATABASE_URL and paste in the value of your Code institute PostgreSQL database,click Add to save.

    In the top layer of your directory create a file env.py, this file needs to be then added to the .gitignore file as this is where the DATABASE_URL and SECRET_KEY variable will be stored.

    The settings.py should be updated to use the DATABASE_URL and SECRET_KEY environment variable values:

      import os
      import dj_database_url
      if os.path.isfile('env.py'):
      import env
<br>

    Replace secret key placeholder with:
    SECRET_KEY = os.environ.get('SECRET_KEY')

    Create a Procfile within the top level of your directory

    Within the Procfile add:

    web: gunicorn project_name.wsgi

    Save all files and Make Migrations: python3 manage.py migrate

    Deploy the branch, when finished click on Open App to visit the live site.

<br>

    Connect your Github Repo to the Heroku App

    Navigate to your deploy tab within your Heroku App

    Select Github as the deployment method, and if prompted confirm that you want to connect to Github. Enter and search for the name of your chosen repository and click on Connect to link them. 

    Return to the deploy tab of the app each time you push changes to Github. 
    Scroll to the bottom and Manually deploy the app by clicking on 'Deploy Branch'. 

7. Credits and Acknowledgments

### Content Sources
Images are from - https://mymum-madeit.com/ - <br>
-This site is just for educational purposes only.- 


### Code References
- Code Institute Tutorials and walkthrough projects

- Documentation references

### Acknowledgments
- Mentor/tutor guidance
- Peer support
- External resources that influenced the project
