## Inschrijvingen / Anmeldungen

{% assign handlers = site.date.deelnemers %}
{% assign count_all = handlers | size %}
{% assign count_nl = handlers | where_exp: "item", "item.land == 'N'" | size %}
{% assign count_de = handlers | where_exp: "item", "item.land == 'D'" | size %}



<h2>NL {{ count_nl }}</h2>
<h2>DE {{ count_de }}</h2>

{% assign update_date = site.data.deelnemers.last.datum %}
1 This page was last updated at {{ update_date | date: "%Y-%m-%d %H:%M" }}.

{% assign update_date = site.data.deelnemers.last %}
2 This page was last updated at {{ update_date.datum | date: "%Y-%m-%d %H:%M" }}.

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
