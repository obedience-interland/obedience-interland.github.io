## Inschrijvingen / Anmeldungen

{% assign youngest = site.data.deelnemers | sort: "datum" | last %}

#### Laatst bijgewerkt op: {{ youngest.datum | date: "%Y-%m-%d" }}.

{% assign handlers = site.data.deelnemers %}
{% assign count_all = handlers | size %}
{% assign count_nl = handlers | where_exp: "item", "item.land == 'N'" | size %}
{% assign count_de = handlers | where_exp: "item", "item.land == 'D'" | size %}

Aantal / Anzahl Nederland : {{ count_nl }}<br/>
Aantal / Anzahl Deutschland : {{ count_de }}<br/>

Aantal per klasse / Anzahl pro Klasse<br/>
- OBB : {{ handlers | where_exp: "h", "h.klasse == 'OBB'" | size }}<br/>
- OB1 : {{ handlers | where_exp: "h", "h.klasse == 'OB1'" | size }}<br/>
- OB2 : {{ handlers | where_exp: "h", "h.klasse == 'OB2'" | size }}<br/>
- OB3 : {{ handlers | where_exp: "h", "h.klasse == 'OB3'" | size }}<br/>

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
