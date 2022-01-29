## Inschrijvingen / Anmeldungen


{% assign nl_count = 1 %}
{% assign nl_count = nl_count + 2 %}
{% assign nl_count = site.data.deelnemers %}

{% for item in items %}
  {% if item.land == 'N' %}
    {% assign nl_count = nl_count + 1 %}
  {% endif %}
{% endfor %}

<h1>{{ nl_count }}</h1>
<h2>{{ site.data.deelnemers.size }} </h2>
<h2>-{{ site.data.deelnemers.land['N'].size }}</h2>
<h2>={{ site.data.deelnemers | where:"land","N" | size }}</h2>
<h2>={{ site.data.deelnemers | where_exp:"ii","ii.land == 'N'" | size }}</h2>
<h2>-{{ site.data.deelnemers.land['N'].size }}</h2>
<h2>-{{ site.data.deelnemers[land == 'D'].size }}</h2>
{% assign update_date = site.data.deelnemers | sort: "date" | first }} </h2>
{% assign update_date = '2020-02-27' %}
This page was last updated at {{ page.update_date | date: "%Y-%m-%d %H:%M" }}.
This page was last updated at {{ update_date | date: "%Y-%m-%d %H:%M" }}.


{% case handle %}
  {% when "cake" %}
     This is a cake
  {% when "cookie", "biscuit" %}
     This is a cookie
<table>
  <thead>
    <tr>
      <th>Nr</th>
      <th></th>
      <th>Handler</th>
      <th>Hond</th>
      <th>Ras</th>
    </tr>
  </thead>
  <tbody>
{% assign items = site.data.deelnemers | sort: 'handler' %}
{% for item in items %}
    <tr>
      <td>{{ item.klasse }}</td>
      <td>{{ item.land }}</td>
      <td>{{ item.handler }}</td>
      <td>{{ item.hond }}</td>
      <td>{{ item.ras }}</td>
    </tr>
{% endfor %}
  </tbody>
</table>
