---
layout: default
---

<section class="directory" id="locations">
  <div class="directory-header">
    <div>
      <p class="eyebrow">Regions</p>
      <h2>Find the most active developers anywhere.</h2>
    </div>
    <div>
      <p>
        Each region is generated from GitHub activity data and includes commits, public contributions,
        private-inclusive totals, organizations, and badge routes.
      </p>
      <div class="directory-stats" aria-label="Region statistics">
        <span><strong>{{ site.data.locations | size }}</strong> regions</span>
        <span><strong data-count="{{ site.data.locations.worldwide.total_user_count }}">{{ site.data.locations.worldwide.total_user_count }}</strong> users worldwide</span>
      </div>
      <label class="region-search" for="region-search">
        <span>Search country</span>
        <input id="region-search" type="search" placeholder="Type a country or region..." autocomplete="off">
      </label>
      <p class="region-search-status" aria-live="polite" data-region-search-status></p>
    </div>
  </div>

  <ul class="country-list">
    {% assign locations = site.data.locations | sort %}
    {% for loc_hash in locations %}
      {% assign region_key = loc_hash[0] %}
      {% assign location = loc_hash[1] %}
      <li>
        <a class="region-card" href="{{ location.page | remove: '.html' }}" data-region-card data-region-title="{{ location.title | downcase }}">
          <span class="region-flag" data-region-key="{{ region_key }}" data-region-title="{{ location.title }}">&#127988;</span>
          <span class="region-copy">
            <span class="region-title">{{ location.title }}</span>
            <span class="region-count"><strong data-count="{{ location.total_user_count }}">{{ location.total_user_count }}</strong> users tracked</span>
          </span>
        </a>
      </li>
    {% endfor %}
  </ul>

  <p class="machine-link">
    Combined machine-readable rankings are available at <a href="rank_only.json">rank_only.json</a>.
  </p>
</section>
