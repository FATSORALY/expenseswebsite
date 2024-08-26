web: gunicorn expenseswebsite.wsgi 
worker: python manage.py qcluster
daphne -u /tmp/daphne.sock expenseswebsite.asgi:application
waitress-serve --host=127.0.0.1 --port=8000 expenseswebsite.wsgi:application
uwsgi --http :8000 --module expenseswebsite.wsgi
