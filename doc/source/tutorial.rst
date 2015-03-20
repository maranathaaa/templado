Tutorial
====================================

Sample json file::

	{
	    "id": {
        	"caption": "Numer faktury",
	        "hint": "np. 21",
	        "type": "text",
	        "order": 1,
	        "check": "^[0-9]+$"
	    },
	    "items": {
	        "caption": "Towary",
	        "order": 2,
	        "type": [
	            {
	                "price": {
	                    "caption": "Cena",
	                    "hint": "np. 21.00",
	                    "type": "text",
	                    "order": 2,
	                    "check": "^[0-9]+\\.[0-9][0-9]$"
	                },
	                "name": {
	                    "caption": "Nazwa towaru",
	                    "hint": "np. slodka bulka",
	                    "type": "text",
	                    "order": 1,
	                    "check": ".+"
	                }
	            }
	        ]
	    }
	}

Sample html file::

	<body>
		<h1>Rachunek nr {{id}}</h1>
		<table>
		{% for a in items %}
		<tr>
			<td>{{ a.name }}</td>
			<td>{{ a.price }}</td>
		</tr>
		{% endfor %}
		</table>
	    <table>
		{% for b in elements %}
		<tr>
			<td>{{ b.name }}</td>
			<td>{{ b.price }}</td>
		</tr>
		{% endfor %}
	    </table>
	</body>

Your own template html for templado app::

	{% extends 'base.html' %}

	{% block title %}
	    {% block templado_title %}
	    {% endblock %}
	{% endblock %}

	{% block content %}
	    {% block templado_static %}
	    {% endblock %}

	    {% block templado_content %}
	    {% endblock %}
	{% endblock %}