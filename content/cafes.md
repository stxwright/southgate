---
title: "Cafe Stops"
date: 2026-01-31
---

A collection of cyclist-friendly cafes around our riding areas in North London, Hertfordshire, and Essex. Opening times may vary, so it's worth checking ahead, especially for larger groups.

<div class="cafe-search">
  <input type="text" id="cafe-search" placeholder="Search cafes by name or area..." />
  <select id="area-filter">
    <option value="">All Areas</option>
    <option value="hertfordshire">Hertfordshire</option>
    <option value="essex">Essex</option>
    <option value="london">London</option>
  </select>
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
        <td>Sophie's</td>
        <td>Hampsthwaite</td>
        <td>4 miles NW</td>
        <td>01423 779219</td>
        <td>Cyclist friendly</td>
      </tr>
      <tr data-area="essex">
        <td>Example Cafe</td>
        <td>Example Town</td>
        <td>8 miles E</td>
        <td>01234 567890</td>
        <td>Great coffee</td>
      </tr>
    </tbody>
  </table>
</div>

## Adding a Cafe

Know a great cafe we should include? [Contact us](/contact/) with the details!

We're particularly interested in cafes that:
- Welcome groups of cyclists
- Have bike parking
- Serve good coffee and food
- Are on popular cycling routes

<script>
document.addEventListener('DOMContentLoaded', function() {
  const searchInput = document.getElementById('cafe-search');
  const areaFilter = document.getElementById('area-filter');
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
