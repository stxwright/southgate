---
title: "Cafe Stops"
date: 2026-01-31
---

A collection of cyclist-friendly cafes around our riding areas in North London, Hertfordshire, and Essex. Opening times may vary, so it's worth checking ahead, especially for larger groups.

<div class="route-controls">
    <div class="search-group">
        <input type="text" id="cafe-search-main" placeholder="Search cafes by name or destination..." />
    </div>
    <div class="filter-group">
        <select id="area-filter-main">
            <option value="">All Areas</option>
            <option value="hertfordshire">Hertfordshire</option>
            <option value="essex">Essex</option>
            <option value="london">London</option>
        </select>
    </div>
</div>

## Our Favorite Stops

<div class="cafes-table-container">
  <table class="cafes-table" id="cafes-table">
    <thead>
      <tr>
        <th>Cafe</th>
        <th>Location</th>
        <th>Distance from Enfield</th>
        <th>Telephone</th>
        <th>Notes</th>
      </tr>
    </thead>
    <tbody>
      <tr data-area="london">
        <td><a href="https://caffenero.com" target="_blank">Caffè Nero</a></td>
        <td>Enfield Town</td>
        <td>0 miles</td>
        <td>-</td>
        <td>Meeting point! ☕</td>
      </tr>
      <tr data-area="hertfordshire">
        <td><a href="https://spokecycles.cc/" target="_blank">Spoke Cycles CC</a></td>
        <td>Codicote</td>
        <td>18 miles N</td>
        <td>01438 488388</td>
        <td>Strong cycling theme, workshop, custom coffee. 🚲</td>
      </tr>
      <tr data-area="hertfordshire">
        <td><a href="https://www.theshedcoffeehouse.co.uk/" target="_blank">The Shed</a></td>
        <td>Sawbridgeworth</td>
        <td>16 miles NE</td>
        <td>01279 723853</td>
        <td>Located in The Maltings. Great coffee and very welcoming. ☕</td>
      </tr>
      <tr data-area="essex">
        <td>The Village Tearoom</td>
        <td>Blackmore</td>
        <td>20 miles E</td>
        <td>01277 821946</td>
        <td>Located on The Green next to the Leather Bottle pub. A classic cycling stop! 🍰</td>
      </tr>
      <tr data-area="hertfordshire">
        <td><a href="http://www.cafetrulyscrumptious.co.uk/" target="_blank">Truly Scrumptious Bistro</a></td>
        <td>Ware</td>
        <td>12 miles N</td>
        <td>01920 460948</td>
        <td>Perfect for relaxed, shorter rides.</td>
      </tr>
    </tbody>
  </table>
</div>

## Adding a Cafe

Know a great cafe we should include? Contact us with the details!

We're particularly interested in cafes that:
- Welcome groups of cyclists
- Have bike parking
- Serve good coffee and food
- Are on popular cycling routes

<script>
document.addEventListener('DOMContentLoaded', function() {
  const searchInput = document.getElementById('cafe-search-main');
  const areaFilter = document.getElementById('area-filter-main');
  const tableRows = document.querySelectorAll('#cafes-table tbody tr');
  
  function filterCafes() {
    const searchTerm = searchInput.value.toLowerCase();
    const areaValue = areaFilter.value;
    
    tableRows.forEach(row => {
      const text = row.textContent.toLowerCase();
      const area = row.dataset.area;
      
      const matchesSearch = text.includes(searchTerm);
      const matchesArea = !areaValue || area === areaValue;
      
      row.style.display = (matchesSearch && matchesArea) ? '' : 'none';
    });
  }
  
  searchInput.addEventListener('input', filterCafes);
  areaFilter.addEventListener('change', filterCafes);
});
</script>
