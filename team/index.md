---
title: Team
nav:
  order: 3
  tooltip: About our team
---

# {% include icon.html icon="fa-solid fa-users" %}Team

{% include section.html %}

{% include list.html data="members" component="portrait" filter="role == 'principal-investigator' and group != 'alum'" %}
{% include list.html data="members" component="portrait" filter="role == 'postdoc' and role != 'phd' and role != 'principal-investigator' and group != 'alum'" %}
{% include list.html data="members" component="portrait" filter="role == 'phd' and role != 'postdoc' and role != 'principal-investigator' and year == 4 and group != 'alum'" %}
{% include list.html data="members" component="portrait" filter="role == 'phd' and role != 'postdoc' and role != 'principal-investigator' and year == 3 and group != 'alum'" %}
{% include list.html data="members" component="portrait" filter="role == 'phd' and role != 'postdoc' and role != 'principal-investigator' and year == 2 and group != 'alum'" %}
{% include list.html data="members" component="portrait" filter="role == 'phd' and role != 'postdoc' and role != 'principal-investigator' and year == 1 and group != 'alum'" %}

{% include section.html %}

## Gallery

<div class="grid">
  {% include feature.html image="images/Gamblingisfun.jpg" %}
  {% include feature.html image="images/Gamblingisfun2.jpg" %}
</div>
  include feature.html
  image="images/Gamblingisfun2.jpg"
  width="100%"
%}

