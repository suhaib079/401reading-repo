# Django Custom User

sometimes we don't want to use only the feilds available in the built in user model or we want to change some feilds , for example we may want to make the user log in by using email instead of the username 

in today's read I will walk with you in the steps of how to create a custom user model
### create app
 create an app and add it in the installed apps in the settings 

- let's call our new app "account"

    INSTALLED_APPS = [

        'account',
    ]
- then add AUTH_USER_MODEL

        AUTH_USER_MODEL = 'account.CustomUser' 
### bulid custem model
custom model inside the app "account" model 

- import AbstractUser

        from django.contrib.auth.models import AbstractUser

- create a class "a model" and let's call it "Account", then fill it with the fields you want

        class CustomUser(AbstractUser):
        pass
        # add additional fields in here
### create new file
 create a new file in the accounts app called forms.py


        touch account/forms.py
### update
update it with the following code to largely subclass the existing forms.

        from django import forms
        from django.contrib.auth.forms import UserCreationForm, UserChangeForm
        from .models import CustomUser

        class CustomUserCreationForm(UserCreationForm):

            class Meta:
                model = CustomUser
                fields = ('username', 'email')

        class CustomUserChangeForm(UserChangeForm):

            class Meta:
                model = CustomUser
                fields = ('username', 'email')


### update admin
 update admin.py since the Admin is highly coupled to the default User model.

        # accounts/admin.py
        from django.contrib import admin
        from django.contrib.auth.admin import UserAdmin

        from .forms import CustomUserCreationForm, CustomUserChangeForm
        from .models import CustomUser

        class CustomUserAdmin(UserAdmin):
            add_form = CustomUserCreationForm
            form = CustomUserChangeForm
            model = CustomUser
            list_display = ['email', 'username',]

        admin.site.register(CustomUser, CustomUserAdmin)

