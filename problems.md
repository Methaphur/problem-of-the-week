---
layout: page
permalink: /problems
permalink_name: /problems
title: Previous Problems

---

Here is a list of previous problems. Click on the links to view the details:

{% for problem in site.problems reversed %}
 -[{{ problem.permalink_name }} - {{ problem.date | date: "%d/%m/%Y" }}]({{site.baseurl}}{{ problem.url }})
{% endfor %}
