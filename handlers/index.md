## Inschrijvingen / Anmeldungen

{% assign youngest = site.data.deelnemers | sort: "datum" | last %}

##### Laatst bijgewerkt op: {{ youngest.datum | date: "%Y-%m-%d" }}.

{% assign handlers = site.data.deelnemers | where_exp: "h", "h.klasse contains 'OB'" %}

### Aantal / Anzahl<br/>

Nederland / Niederlande : {{ handlers | where: 'land', 'N' | size }}<br/>
Duitsland / Deutschland : {{ handlers | where: 'land', 'D' | size }}<br/>

### Aantal per klasse / Anzahl pro Klasse<br/>

<table>
<tr><td>OB B</td><td>{{ handlers | where: 'klasse', 'OB B' | size }}</td></tr>
<tr><td>OB 1</td><td>{{ handlers | where: 'klasse', 'OB 1' | size }}</td></tr>
<tr><td>OB 2</td><td>{{ handlers | where: 'klasse', 'OB 2' | size }}</td></tr>
<tr><td>OB 3</td><td>{{ handlers | where: 'klasse', 'OB 3' | size }}</td></tr>
</table>

### Ingeschreven deelnemers / registrierten Teilnehmern

<table>
  <thead>
    <tr>
      <th>Klasse</th>
      <th></th>
      <th>Handler</th>
      <th>Hond</th>
      <th>Ras</th>
    </tr>
  </thead>
  <tbody>
{% assign items = handlers %}
{% for item in items %}
    <tr align="left">
      <td>{{ item.klasse }}</td>
      <td>{{ item.land }}</td>
      <td>{{ item.handler }}</td>
      <td>{{ item.hond }}</td>
      <td>{{ item.ras }}</td>
    </tr>
{% endfor %}
  </tbody>
</table>
