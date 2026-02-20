---
layout: page
nav_order: 0
hide_right_toc: true
---

{%- assign instructors = site.staffers | where: 'role', 'Instructor' | map: "name" -%}
{%- assign instructor_msg = "Instructor" -%}
{%- if instructors.size != 1 -%}
{%- assign instructor_msg = "Instructors" -%}
{%- endif -%}

<img align="right" alt="{{ site.title }} logo" width="85px" src="{{ site.logo | relative_url }}">

# {{ site.title }}

{% if instructors.size != 0 %}
<span style="white-space: nowrap;">
    <strong>{{instructor_msg}}</strong>: {{ instructors | join: ", " }}{%- if site.lecture.time != empty %} / {%- endif -%}
</span>
{% endif -%}
{%- if site.lecture.time != empty -%}
<span style="white-space: nowrap;">
    <strong>Lecture</strong>: {{ site.lecture.time }}
    {%- if site.lecture.location.name != empty and site.lecture.location.link != empty -%}
    , [{{site.lecture.location.name}}]({{site.lecture.location.link}})
    {%- elsif site.lecture.location.name != empty -%}
    , {{site.lecture.location.name}}
    {%- endif -%}
</span>
{% endif -%}

{%- if site.heading_links.size != 0 -%}
<!-- <span style="white-space: nowrap;">
    [
    {%- for link in site.heading_links -%}
    {%- unless forloop.first -%}, {% endunless -%}
    {%- if link.text != empty and link.url != empty -%}
    [{{link.text}}]({{link.url}})
    {%- elsif link.text != empty -%}
    {{link.text}}
    {%- endif -%}
    {%- endfor -%}
    ]
</span> -->
{% endif -%}

## Presistent Announcements

<!-- - **Enroll** for Fall 2025 [here](http://berkie.ee/bhjq05)! -->

<!--- **Lecture**: Fridays 3-4:30pm in [BWRC](https://www.google.com/search?q=berkeley+wireless+research+center). Ring the doorbell to be let in! We will meet in the big central room.-->

- You will find labs and project repositories on our [GitHub](https://github.com/ucb-eecs151tapeout).

- When in doubt, ask on the Discord: [berkie.ee/151t-discord](https://berkie.ee/151t-discord).

- You can also email us at [151tapeout@ieee.berkeley.edu](151tapeout@ieee.berkeley.edu).


{%- if site.enable_announcements -%}

{{ site.announcements.last }}

[Past announcements](announcements){: .btn .btn-outline .fs-3 }
{%- endif %}

## Course Calendar

[Skip to current week](#week-{{ 'now' | date: '%U' }}){: .btn .btn-outline .fs-3 }

<div>
{%- include syllabus.html -%}
</div>
