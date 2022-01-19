## Inschrijvingen / Anmeldungen

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
