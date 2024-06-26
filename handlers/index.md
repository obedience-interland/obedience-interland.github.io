## Inschrijvingen / Anmeldungen

{% assign youngest = site.data.deelnemers | sort: "datum" | last %}

##### Bijgewerkt tot: {{ youngest.datum | date: "%Y-%m-%d" }}.

{% assign handlers = site.data.deelnemers | where_exp: "h", "h.klasse contains 'OB'" %}

### Aantal per klasse / Anzahl pro Klasse

{% assign handlersNL = handlers | where: 'land', 'N' %}
{% assign handlersDE = handlers | where: 'land', 'D' %}

|    | Beginners | Klasse 1 | Klasse 2 | Klasse 3 || Totaal |
| :-- | -- | -- | -- | -- |--| -- |
| Nederland   | {{ handlersNL | where: 'klasse', 'OB B' | size }} | {{ handlersNL | where: 'klasse', 'OB 1' | size }} | {{ handlersNL | where: 'klasse', 'OB 2' | size }} | {{ handlersNL | where: 'klasse', 'OB 3' | size }} || {{ handlers | where: 'land', 'N' | size }} |
| Deutschland | {{ handlersDE | where: 'klasse', 'OB B' | size }} | {{ handlersDE | where: 'klasse', 'OB 1' | size }} | {{ handlersDE | where: 'klasse', 'OB 2' | size }} | {{ handlersDE | where: 'klasse', 'OB 3' | size }} || {{ handlers | where: 'land', 'D' | size }} |
| Totaal      | {{ handlers | where: 'klasse', 'OB B' | size }} | {{ handlers | where: 'klasse', 'OB 1' | size }} | {{ handlers | where: 'klasse', 'OB 2' | size }} | {{ handlers | where: 'klasse', 'OB 3' | size }} || {{ handlers | size }} |

### Ingeschreven deelnemers / registrierten Teilnehmern

<table>
  <thead>
    <tr>
      <th>Nr</th>
      <th>Klasse</th>
      <th></th>
      <th>Handler</th>
      <th>Hond</th>
      <th>Ras</th>
    </tr>
  </thead>
  <tbody>
{% assign items = handlers | sort: 'nr' %}
{% for item in items %}
    <tr align="left">
      <td>{{ item.nr }}</td>
      <td>{{ item.klasse }}</td>
      <td>{{ item.land }}</td>
      <td>{{ item.handler }}</td>
      <td>{{ item.hond }}</td>
      <td>{{ item.ras }}</td>
    </tr>
{% endfor %}
  </tbody>
</table>
