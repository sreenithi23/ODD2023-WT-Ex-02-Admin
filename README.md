# Ex-02-Admin
Ex-03-Admin User using function-based views
Name:SREENITHI
Ref no:23006660
### AIM:
Create a Django website with five users. Two users are to be staff users (including admin) and the other three users are non-staff users. 1.Creating five users

2.Two staff users and three non-staff users

3.Setting e-mail for all users

4.Setting the first name and last name for all users.

### Design Procedure

### step 1:Create a Django Project
Create a Django Project django-admin startproject myproject

### step 2:Create a Django App
Create a Django app within your project using the following command: cd myproject python manage.py startapp myapp.

### step 3:Define User Creation View
In your app's views.py file (myapp/views.py), define a view function to create the users with the specified attributes.

To Create a Django website with five users (Two staff users,including an admin, ans three non_staff users),set email,first name and last name for all users,you can use the following python view function:
```
from django.contrib.auth.models import User
from django.views import View
from django.shortcuts import render

def create_users(request):
    admin_user=User.objects.create_user(username='admin',password='adminpass')
    admin_user.is_staff = True
    admin_user.is_superuser = True
    admin_user.email = 'admin@example.com'
    admin_user.first_name = 'Admin'
    admin_user.last_name = 'User'
    admin_user.save()

    staff_user1 = User.objects.create_user(username = 'staff1',password='staffpass'
    staff_user.is_staff = True
    staff_user.email = 'staff1@example.com'
    staff_user.first_name = 'Staff'
    staff_user.last_name = 'User1'
    staff_user.save()

    user1 = User.objects.create_user(username = 'staff1',password='staffpass'
    user1.email = 'staff1@example.com'
    user1.first_name = 'User'
    user1.last_name = 'One'
    user1.save()

    user2 = User.objects.create_user(username = 'staff1',password='staffpass'
    user2.email = 'staff1@example.com'
    user2.first_name = 'User'
    user2.last_name = 'Two'
    user2.save()

    user3 = User.objects.create_user(username = 'staff1',password='staffpass'
    user3.email = 'staff1@example.com'
    user3.first_name = 'User'
    user3.last_name = 'Three'
    user3.save()

    return render(request,'myfirstapp/user_creation_success.html')
```
### step 4:Create Templates
Create a template directory within your app (myapp/templates) if it doesn't already exist. Inside this directory, create a template named 'user_creation_success.html' to display a success message.
```
<html>
    <body>
        <h1>
            Successfully Created
        </h1>
    </body>
</html>
Step 5:Define URL Pattern In your app's urls.py file (myapp/urls.py), define a URL pattern to route to the create_users view.

from django.contrib import admin
from django.urls import path

from myapp import views
from myapp.views import create_users


urlpatterns = [
    path('admin/', admin.site.urls),
    path('create_users/',views.create_users,name='create_users'),
]
```
### Step 6: Apply Migrations
Apply migrations to create the necessary database tables for the User model. python manage.py makemigrations python manage.py migrate

### Step 7: Run the Development Server
Start the development server to run your Django application. python manage.py runserver

### Step 8: Access the User Creation View
Access the User Creation View by Visit http://localhost:8000/create_users/ in your web browser to execute the create_users view and create the users.

### Step 9: Veriy the Users
You can verify that the users have been created with the specified attributes by checking the Django admin interface.

### OUTPUT:
![Screenshot 2023-12-29 204743](https://github.com/sreenithi23/ODD2023-WT-Ex-02-Admin/assets/147017600/8f346be6-99c3-4670-85f7-0f8ed9e52759)
### RESULT:
The output is verified successfully

