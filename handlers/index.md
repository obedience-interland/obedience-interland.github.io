## Inschrijvingen / Anmeldungen


{% assign nl_count = 1 %}
{% assign nl_count = nl_count + 2 %}
{% assign items = site.data.deelnemers %}
{% for item in items %}
  {% if item.land == 'N' %}
    {% assign nl_count = nl_count + 1 %}
  {% endif %}
{% endfor %}

<h1>{{ nl_count }}</h1>
<h2>{{ site.data.deelnemers.size }} </h2>
<h2>-{{ site.data.deelnemers.land['N'].size }}</h2>
<h2>-{{ site.data.deelnemers[land == 'D'].size }}</h2>
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
