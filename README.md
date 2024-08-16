# Django-Restaurant-Project

Little Lemon Restaurant App Documentation
1. Project Overview
The Little Lemon Restaurant app is a web-based application designed to manage restaurant bookings and display menu items. Users can book tables, view the restaurant's menu, and explore detailed information about each menu item.
Features
-	Home Page: A welcoming landing page.
-	About Page: Information about the restaurant.
-	Booking Page: Allows users to book a table at the restaurant.
-	Menu Page: Displays a list of available menu items.
-	Menu Item Details: Provides detailed descriptions of individual menu items.
Technologies Used
-	Backend Framework: Django 4.1.1
-	Database: SQLite (default for development)
-	Frontend: Django templates with basic HTML and CSS.
-	Middleware: Standard Django middleware.
2. Installation
Requirements
-	Python 3.8+
-	Django 4.1.1
-	SQLite (default, no additional setup required)
Setup Instructions
1.	Clone the Repository:
   git clone https://github.com/yourusername/littlelemon.git    cd littlelemon
2.	Create a Virtual Environment:
   python -m venv venv    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
3.	Install Dependencies:
   pip install -r requirements.txt
4.	Set Up the Database:    python manage.py migrate
5.	Run the Development Server:    python manage.py runserver
The application will be available at http://127.0.0.1:8000/.
3. Configuration
Settings
-	DEBUG: Set to True for development. Change to False in production.
-	ALLOWED_HOSTS: Empty list by default. Update this for production with your domain or IP.
-	INSTALLED_APPS: Includes the restaurant app.
-	TEMPLATES: Configured to use templates from the restaurant/templates directory.
-	DATABASE: Default SQLite setup (db.sqlite3).
-	STATICFILES_DIRS: Configured to load static files from restaurant/static.
Environment Variables
-	SECRET_KEY: The Django secret key is stored in the settings.py. Replace it with an environmentvariable in production.
4. Models
Booking
-	Fields:
-	first_name: CharField (max_length=200)
-	last_name: CharField (max_length=200)
-	guest_number: IntegerField
-	comment: CharField (max_length=1000)
-	Description: Manages customer bookings.
-	String Representation: Returns the first_name and last_name.
Menu
-	Fields:
-	name: CharField (max_length=200)
-	price: IntegerField
-	description: TextField (max_length=1000, default='')
-	Description: Represents menu items.
-	String Representation: Returns the name of the menu item.
5. API Documentation
Endpoints
-	Home: GET / - Displays the home page.
-	About: GET /about/ - Displays the about page.
-	Book: GET /book/ - Displays the booking form.
-	POST /book/ - Submits booking form data.
-	Menu: GET /menu/ - Displays the menu items.
-	Menu Item: GET /menu_item/<int:pk>/ - Displays details of a specific menu item.
6. Views and Templates
Views
-	home(request): Renders the index.html template.
-	about(request): Renders the about.html template.
-	book(request): Handles the booking form; renders book.html.
-	menu(request): Fetches and displays all menu items in menu.html.
-	display_menu_items(request, pk): Fetches and displays details of a specific menu item inmenu_item.html.
Templates
-	index.html: Home page template.
-	about.html: About page template.
-	book.html: Booking form template.
-	menu.html: Menu list template.
-	menu_item.html: Detailed menu item template.
7. Forms
BookingForm
-	Model: Uses the Booking model.
-	Fields: All fields (first_name, last_name, guest_number, comment) are included.
-	Usage: This form is used to create and manage restaurant bookings.
8. Deployment
Production Setup
-	Debugging: Set DEBUG = False.
-	Static Files: Configure a proper static file server for production (e.g., WhiteNoise, Nginx).
-	Database: Replace SQLite with a production-grade database like PostgreSQL or MySQL.
Server Configuration
-	WSGI Application: Use littlelemon.wsgi.application as the entry point for WSGI servers likeGunicorn or uWSGI.
9. Troubleshooting
Common Issues
-	Migrations: If migrations fail, try running python manage.py makemigrations and then pythonmanage.py migrate.
-	Static Files: Ensure STATICFILES_DIRS is correctly configured to serve static files.
10. Contributing
Contribution Guidelines
-	Fork the repository and create a new branch for your feature or bug fix.
-	Submit a pull request with a detailed description of your changes.
Code Style
-	Follow PEP 8 guidelines for Python code.
-	Use Django best practices for views, models, and templates.
11.	Changelog
Version 1.0.0: Initial release with basic features for booking, menu display, and item details.
12.	License
This project is licensed under the MIT License. See the LICENSE file for details.
13. Credits and Acknowledgments
Django Documentation: For framework guidance.
Bootstrap: For responsive web design elements used in templates.
14. Appendix
Additional Resources
-	Django Documentation: https://docs.djangoproject.com/en/4.1/
-	Django REST Framework: https://www.django-rest-framework.org/
-	SQLite Documentation: https://sqlite.org/docs.html
