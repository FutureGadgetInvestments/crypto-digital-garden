---
layout: page
title: All Research
permalink: /research/
---

Browse all research in this garden.

<div class="view-toggle">
  <button class="view-btn active" data-view="category">By Category</button>
  <button class="view-btn" data-view="status">By Status</button>
  <button class="view-btn" data-view="alphabetical">A-Z</button>
</div>

<div id="view-category" class="research-view active">

### Perp DEX Liquidity Pools
{% assign perp_dex = site.research | where: "category", "perp-dex-liquidity-pools" | sort: "title" %}
{% if perp_dex.size > 0 %}
<ul>
{% for item in perp_dex %}
  <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a>{% if item.status %} <span class="status-badge status-{{ item.status }}">{{ item.status }}</span>{% endif %}</li>
{% endfor %}
</ul>
{% else %}
*No research yet.*
{% endif %}

### Stable Coins
{% assign stablecoins = site.research | where: "category", "stable-coins" | sort: "title" %}
{% if stablecoins.size > 0 %}
<ul>
{% for item in stablecoins %}
  <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a>{% if item.status %} <span class="status-badge status-{{ item.status }}">{{ item.status }}</span>{% endif %}</li>
{% endfor %}
</ul>
{% else %}
*No research yet.*
{% endif %}

### Zero Coupon Bonds
{% assign zcb = site.research | where: "category", "zero-coupon-bonds" | sort: "title" %}
{% if zcb.size > 0 %}
<ul>
{% for item in zcb %}
  <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a>{% if item.status %} <span class="status-badge status-{{ item.status }}">{{ item.status }}</span>{% endif %}</li>
{% endfor %}
</ul>
{% else %}
*No research yet.*
{% endif %}

</div>

<div id="view-status" class="research-view">

### Evergreen
{% assign evergreen = site.research | where: "status", "evergreen" | sort: "title" %}
{% if evergreen.size > 0 %}
<ul>
{% for item in evergreen %}
  <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a>{% if item.category %} <span class="category-badge">{{ item.category }}</span>{% endif %}</li>
{% endfor %}
</ul>
{% else %}
*No evergreen research yet.*
{% endif %}

### Budding
{% assign budding = site.research | where: "status", "budding" | sort: "title" %}
{% if budding.size > 0 %}
<ul>
{% for item in budding %}
  <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a>{% if item.category %} <span class="category-badge">{{ item.category }}</span>{% endif %}</li>
{% endfor %}
</ul>
{% else %}
*No budding research yet.*
{% endif %}

### Seedling
{% assign seedling = site.research | where: "status", "seedling" | sort: "title" %}
{% if seedling.size > 0 %}
<ul>
{% for item in seedling %}
  <li><a href="{{ item.url | relative_url }}">{{ item.title }}</a>{% if item.category %} <span class="category-badge">{{ item.category }}</span>{% endif %}</li>
{% endfor %}
</ul>
{% else %}
*No seedling research yet.*
{% endif %}

</div>

<div id="view-alphabetical" class="research-view">

{% assign all_research = site.research | sort: "title" %}
<ul class="note-list">
{% for item in all_research %}
  <li>
    <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
    {% if item.category %}
    <span class="category-badge">{{ item.category }}</span>
    {% endif %}
    {% if item.status %}
    <span class="status-badge status-{{ item.status }}">{{ item.status }}</span>
    {% endif %}
  </li>
{% endfor %}
</ul>

</div>

<style>
.view-toggle {
  display: flex;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.view-btn {
  padding: 0.5rem 1rem;
  border: 1px solid #ccc;
  background: #f5f5f5;
  cursor: pointer;
  border-radius: 4px;
  font-size: 0.9rem;
  transition: all 0.2s ease;
}

.view-btn:hover {
  background: #e0e0e0;
}

.view-btn.active {
  background: #333;
  color: #fff;
  border-color: #333;
}

.research-view {
  display: none;
}

.research-view.active {
  display: block;
}

.category-badge {
  font-size: 0.75rem;
  padding: 0.15rem 0.4rem;
  background: #e8f4f8;
  border-radius: 3px;
  margin-left: 0.5rem;
  color: #2c5282;
}

.status-badge {
  font-size: 0.75rem;
  padding: 0.15rem 0.4rem;
  border-radius: 3px;
  margin-left: 0.5rem;
}

.status-seedling {
  background: #fef3c7;
  color: #92400e;
}

.status-budding {
  background: #d1fae5;
  color: #065f46;
}

.status-evergreen {
  background: #a7f3d0;
  color: #047857;
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const buttons = document.querySelectorAll('.view-btn');
  const views = document.querySelectorAll('.research-view');

  buttons.forEach(button => {
    button.addEventListener('click', function() {
      const viewName = this.getAttribute('data-view');

      // Update button states
      buttons.forEach(btn => btn.classList.remove('active'));
      this.classList.add('active');

      // Update view visibility
      views.forEach(view => view.classList.remove('active'));
      document.getElementById('view-' + viewName).classList.add('active');
    });
  });
});
</script>
