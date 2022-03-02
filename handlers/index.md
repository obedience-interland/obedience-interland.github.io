## Inschrijvingen / Anmeldungen

{% assign youngest = site.data.deelnemers | sort: "datum" | last %}

##### Laatst bijgewerkt op: {{ youngest.datum | date: "%Y-%m-%d" }}.

{% assign handlers = site.data.deelnemers | where_exp: "h", "h.klasse != 'XXX'" %}

### Aantal / Anzahl<br/>

- Nederland / Niederlande : {{ handlers | where_exp: "h", "h.land == 'N'" | size }}<br/>
- Duitsland / Deutschland : {{ handlers | where_exp: "h", "h.land == 'D'" | size }}<br/>

### Aantal per klasse / Anzahl pro Klasse<br/>

- OBB : {{ handlers | where_exp: "h", "h.klasse == 'OBB'" | size }}<br/>
- OB1 : {{ handlers | where_exp: "h", "h.klasse == 'OB1'" | size }}<br/>
- OB2 : {{ handlers | where_exp: "h", "h.klasse == 'OB2'" | size }}<br/>
- OB3 : {{ handlers | where_exp: "h", "h.klasse == 'OB3'" | size }}<br/>

### Ingeschreven deelnemers / registrierten Teilnehmern

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
{% assign items = site.data.deelnemers | where_exp: "h", "h.betaald == '1'" | sort: 'handler' %}
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
