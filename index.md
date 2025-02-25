---
---
<h1>Test</h1>
{{ site.data.meta.fkgt_5107_art_invas_p.f_table_name }}

<table border="1">
<tr><th>Feltnavn</th><th>Feltnavn10</th><th>Formål</th><th>Datatype</th><th>Værdiområde</th><th>Obligatorisk/frit</th><th>Eksempel</th><th>Systemfelt</th></tr>

{% for field in site.data.meta.fkgt_5107_art_invas_p.fields %}

<tr>
{% assign column = site.data.fkg.tables.t_5107_art_invas_p_t.columns | where: "name",field[0] %}

{% assign system = true %}
{% if column[0].name == field[0] %}
    {% assign system = false %}
{% endif %}

{% assign checks = column[0]._checks[0] %}

{% if field[1].restriction != null %}
    {% assign system = field[1].restriction %}
{% endif %}

<td>{{ field[0] }}</td><td>10 tegn</td><td>{{ field[1].comment }}</td><td>{{ field[1].full_type }}</td><td>{{ checks }}</td><td>{{ column[0].is_nullable }}</td><td>fx</td><td>{{ system }}</td>

</tr>

{% endfor %}

</table>
