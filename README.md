# Project Name

## Table of Contents
- [Overview](#overview)
- [User Experience (UX)](#user-experience-ux)
- [Features](#features)
- [Data Schema](#data-schema)
- [Technologies Used](#technologies-used)
- [Testing](#testing)
- [Deployment](#deployment)
- [Credits](#credits)

1. Overview

## Project Purpose
<strong>Clear description of the application's purpose</strong>
This is an online fashion retail website specializing in women's clothing with a focus on???
The site features a curated collection of clothing and accessories ???

<strong>Value it provides to users</strong>
-Offers a carefully curated selection of cohesive, feminine clothing pieces
- Delivers a seamless shopping experience with professional product photography
- Offers pieces that coordinate well together, making outfit planning easier

<strong>Target audience identification</strong>
- Women who value quality over fast fashion trends
- Those looking for coordinated wardrobe pieces rather than individual statement items

<strong>Real-world problem it solves</strong>
- Eliminates the overwhelming choice paralysis common in fast fashion retail
- Addresses the difficulty of finding cohesive, feminine clothing pieces that work together???
- Solves the problem of inconsistent quality and style across different fashion retailers???
- Provides an alternative to mass-market fashion for women seeking more distinctive, modest styling???

### Project Rationale
<strong>Justified rationale for development</strong>
- The fashion e-commerce space is dominated by fast fashion retailers offering overwhelming product selections that often lack cohesion. There's a clear opportunity for a curated, quality-focused alternative that serves customers seeking ???
- Growing consumer awareness about sustainable fashion and quality clothing has created demand for retailers that prioritize curation over volume, justifying a premium positioning strategy.

<strong>Why this solution was chosen</strong>
- The minimilst design interface prioritizes product visibility and easy navigation over flashy design elements, allowing the clothing to be the focal point and reducing visual clutter that can overwhelm users.
- A cohesive identity creates a strong brand identity that 

<strong>How it addresses user needs and expectations</strong>
- Streamlined shopping experience 

2. User Experience (UX)

### User Stories
- Comprehensive user stories for different user types
- Acceptance criteria for each story
- How the final application aligns with these stories

### Design Process
- UX design work undertaken
- Reasoning behind design decisions
- Information hierarchy considerations
- User control principles applied
- Consistency across the application
- Accessibility guidelines followed

### Wireframes
<details>
    <summary>Entity Relationship Diagram (ERD)</summary>
    <br>
    <img src="" alt="">
    </details>

- Include wireframes, mock-ups, and diagrams
- Design process documentation
- Any design decisions that contravene accepted UX principles (with justification)

### Front-end Design Principles
- Information hierarchy implementation?????
- User control features
- Consistency across pages/sections
- Confirmation and feedback systems
- Accessibility compliance

3. Features

### Existing Features
- Main navigation menu and structured layout
- User authentication (registration/login/logout)
- Form validation and user feedback
- CRUD functionality for all models
- E-commerce payment system integration
- Error handling and user notifications
- Responsive design implementation

### Apps Structure
<strong>My apps</strong>
- Home
- Products
- Bag
- Checkout
- Profiles 
<br>

<strong>How each app represents a natural aspect of the project</strong>

<strong>Explanation of app separation logic</strong>

<strong>Shared data between apps (no duplication)</strong>

### Future Features
- Planned enhancements
- Additional functionality considerations

<br>
4. Data Schema
<br>
<details>
    <summary>Entity Relationship Diagram (ERD)</summary>
    <br>
    <img src="" alt="">
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

<strong>Field Explanations and Relationships</strong>

- Order Model Fields:

order_number (char): Unique identifier for tracking orders
user_profile (bigint): Foreign key linking to User Profile for registered customers
Customer details: full_name, email, phone_number for order fulfillment
Address fields: Complete delivery address breakdown for shipping
Financial fields: delivery_cost, order_total, grand_total (decimal) for accurate pricing
Payment processing: original_bag (text), stripe_pid (char) for transaction tracking
date field for order timestamp

- OrderLineItem Model Fields:

order (char): Foreign key reference to parent Order
product (char): Foreign key reference to specific Product
product_size (char): Product variant specification
quantity (bigint): Number of items ordered
line_item_total (decimal): Calculated total for this line item

- User Profile Model Fields:

user (char): One-to-one relationship with Django's built-in User model
Default address fields: Pre-populated shipping information for faster checkout
All address fields mirror the Order model for consistency

- Category Model Fields:

name (char): Internal category identifier
friendly_name (char): Customer-facing display name

- Product Model Fields:

category (char): Foreign key to Category model
sku (char): Stock keeping unit for inventory management
name (char): Product title
colour (char): Product color variant
description (text): Detailed product information
has_sizes (boolean): Indicates if product has size variants
price (decimal): Product pricing
rating (decimal): Customer rating system
image_url (varchar): External image reference
image (bigint): Direct image file storage

<strong>Field Explanations and Relationships</strong>
Order Model Fields:

order_number (char): Unique identifier for tracking orders
user_profile (bigint): Foreign key linking to User Profile for registered customers
Customer details: full_name, email, phone_number for order fulfillment
Address fields: Complete delivery address breakdown for shipping
Financial fields: delivery_cost, order_total, grand_total (decimal) for accurate pricing
Payment processing: original_bag (text), stripe_pid (char) for transaction tracking
date field for order timestamp

OrderLineItem Model Fields:

order (char): Foreign key reference to parent Order
product (char): Foreign key reference to specific Product
product_size (char): Product variant specification
quantity (bigint): Number of items ordered
line_item_total (decimal): Calculated total for this line item

User Profile Model Fields:

user (char): One-to-one relationship with Django's built-in User model
Default address fields: Pre-populated shipping information for faster checkout
All address fields mirror the Order model for consistency

Category Model Fields:

name (char): Internal category identifier
friendly_name (char): Customer-facing display name

Product Model Fields:

category (char): Foreign key to Category model
sku (char): Stock keeping unit for inventory management
name (char): Product title
colour (char): Product color variant
description (text): Detailed product information
has_sizes (boolean): Indicates if product has size variants
price (decimal): Product pricing
rating (decimal): Customer rating system
image_url (varchar): External image reference
image (bigint): Direct image file storage

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

    ERROR HANDLING

<strong>Data Validation/ Security with Stripe</strong>


### Models
- Detailed description of custom Django models
- Field explanations and relationships
- Data validation implemented
- How models support user stories

### CRUD Operations
- Full CRUD functionality documentation
- How actions are reflected in the user interface
- Data validation and error handling

Shop owner CRUD functionality 
Site user/ client CRUD functionality

5.  Technologies Used

https://jsonformatter.org/ 
https://imagecolorpicker.com/
https://unsplash.com/photos/a-delicate-painting-of-a-white-hyacinth-mn81rQG7wIQ 
https://www.w3schools.com/ 

### Languages
- Python
- HTML5
- CSS3
- JavaScript

### Frameworks and Libraries
- Django (version)
- Bootstrap/other CSS frameworks
- JavaScript libraries used

### Database
- Database system used
- Configuration details

### Payment Processing
- Stripe
- Security considerations

### Other Tools
- Version control (Git)
- Development environment
- Deployment platform



### Requirements 



### External Code Attribution
- Clear separation between custom code and external sources
- Attribution for all external code via comments
- Library dependencies listed

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
|Accessibility | | | |
| | | | |

<strong>Lighthouse</strong>


- Test-driven development approach
- Testing procedures followed
- Coverage level achieved

- Responsive design testing
- Accessibility testing

### Responsive Testing
- Browsers: Chrome, Firefox, Safari, Edge
- Devices: Desktop, Tablet, Mobile

### Validation

<details>
    <summary>HTML validation (W3C)</summary>
    <br>
    <img src="" alt="">
    </details>


<details>
    <summary>CSS validation (Jigsaw)</summary>
    <br>
    <img src="" alt="">
    </details>


<details>
    <summary>JavaScript validation (JSHint)</summary>
    <br>
    <img src="" alt="">
    </details>


<details>
    <summary>Python code style (PEP8)</summary>
    <br>
    <img src="" alt="">
    </details>


### Bug Fixes
- Known issues and their resolutions

BUGS

- Outstanding bugs (if any)

6.  Deployment

### Live Site
- Link to deployed application
- Confirmation that deployed version matches development

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

Replace secret key placeholder with:

  SECRET_KEY = os.environ.get('SECRET_KEY')

Create a Procfile within the top level of your directory

Within the Procfile add:

  web: gunicorn project_name.wsgi

    Save all files and Make Migrations: python3 manage.py migrate

    Deploy the branch, when finished click on Open App to visit the live site.


Connect your Github Repo to the Heroku App

- Navigate to your deploy tab within your Heroku App
- Select Github as the deployment method, and if prompted confirm that you want to connect to Github. Enter and search for the name of your chosen repository and click on Connect to link them. 
- Return to the deploy tab of the app each time you push changes to Github. Scroll to the bottom and Manually deploy the app by clicking on 'Deploy Branch'. 





- Database deployment documentation
- Environment variables setup
- Configuration file management

### Local Development Setup
- Instructions for running locally
- Requirements installation
- Database setup
- Environment configuration

### Security Considerations
- Environment variables for sensitive data
- Debug mode configuration
- Password and secret key management
- User permission levels

### Configuration Management
- Settings file organization
- Different configurations for different environments
- Data store configuration location

7. Version Control

### Git Usage
- Repository structure
- Commit message standards
- Branching strategy
- Development process documentation

### Development Process
- Clear commit history showing TDD approach
- Individual commits for each feature/fix
- No large commits that obscure development process
- Configuration file versioning

8. Credits

### Content Sources
- Text content attribution
- Image sources and credits
- Data sources

### Code References
- Tutorial or walkthrough acknowledgments
- Stack Overflow solutions used
- Documentation references

### Acknowledgments
- Mentor/tutor guidance
- Peer support
- External resources that influenced the project

---

## Additional Documentation Considerations

### README Quality Standards
- Well-structured markdown formatting
- Consistent formatting throughout
- Clear section organization
- Professional presentation
- Few errors in spelling and grammar
- Easy to follow and understand

### Evidence of Craftsmanship
- Code organization and cleanliness
- Framework conventions followed
- Security best practices implemented
- Comprehensive error handling
- Professional-grade user interface
- Original work (not copy of walkthrough projects)