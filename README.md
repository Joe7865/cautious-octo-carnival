# cautious-octo-carnival
I'm not sure what this is going to be yet (hence the name).

## mysite
This is currently just the basic Django template created by following the offcial tutorial at https://docs.djangoproject.com/en/4.1/intro/tutorial01/. 

### To start this project

Run `py manage.py runserver` inside the mysite folder.

The user interface is then viewable at: http://localhost:8000/

### Migrations

Run `python manage.py migrate` to create any tables necessary for installed apps in settings.py. Migrations can be used to live update a database avoiding downtime for your application.

Run `python manage.py makemigrations polls` if you have made changes to your models and would like them to be installed as migrations.

Run something similar to `python manage.py sqlmigrate polls 0001` to check which SQL commands the migration would run on the database.

remember the three-step guide to making model changes:

1. Change your models (in models.py).
2. Run python manage.py makemigrations to create migrations for those changes
3. Run python manage.py migrate to apply those changes to the database.

### Database api

Open python shell with the required environement variables set `py manage.py shell`.

Then you can add/update/delete rows using this api:
- Import required models `from polls.models import Choice, Question`
- List all current rows from Question table `Question.objects.all()`
- You might need other imports `from django.utils import timezone`
- Create new instance of question `q = Question(question_text="What's new?", pub_date=timezone.now())`
- Save instance to DB `q.save()`
- Retrieve a property from the db `q.id`
- Modify a row `q.question_text = "What's up?"` (You will have to save again afterwards).
- Lookup with filter `Question.objects.filter(id=1)` or `Question.objects.filter(question_text__startswith='What')`.
- Get existing row `q = Question.objects.get(pk=1)`
- Get a related set of objects `q.choice_set.all()`
- Create a new choice linked to a question and capture the new choice `c = q.choice_set.create(choice_text='Just hacking again', votes=0)`
- Delete a row `c.delete()`
- Count rows `q.choice_set.count()`

### Admin user (Next step in tutorial 2)

## src
I am not sure what this is yet.
