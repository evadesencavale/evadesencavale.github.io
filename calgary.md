---
layout: trip-preparation
---
<html>
  <head>
    <title>Calgary</title>
    <style>
      @import
  "minima/skins/{{ site.minima.skin | default: 'classic' }}",
  "minima/initialize";
      
      table {
        border-collapse: collapse;
        width: 100%;
      }

      th, td {
        text-align: left;
        padding: 8px;
      }

      th {
        cursor: pointer;
      }

      th:hover {
        background-color: #ddd;
      }
    </style>

    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script src="https://cdn.jsdelivr.net/jquery.tablesorter/2.33.3/js/jquery.tablesorter.min.js"></script>
    <script>
    $(document).ready(function() {
      $("#myTable").tablesorter();
    });
    </script>
    
  </head>
  <body>
    <main>
      <h1>Calgary</h1>
      
      <table id="myTable">
        <thead>
          <tr>
            <th class="header">Column 1</th>
            <th class="header">Column 2</th>
            <th class="header">Column 3</th>
          </tr>
        </thead>
        <tbody>
          {% for item in site.data.calgary_data %}
            <tr>
              <td>{{ item.column1 }}</td>
              <td>{{ item.column2 }}</td>
              <td>{{ item.column3 }}</td>
            </tr>
          {% endfor %}
        </tbody>
      </table>

      
      
      
      
      
      
      
      
      
      
      
      <!--<ul>
        <li><a href="https://www-1561q.bookeo.com/bookeo/b_trapped-calgary_start.html?ctlsrc2=g8YFBrkyGFGxllI3fEbLTkp8ABTERZ6X0zkIY3H8BVE%3D&src=02h">Trapped Calgary</a></li>
        <ul>
          <li>Attention, posiblement des salles identiques à d'autres succursales de Trapped, comme Markham</li>
          <li>Jeux</li>
          <ul>
            <li>Chaos Effect (Recommandé par Errol)</li>
            <li>Jack the Ripper</li>
            <li>Ancient Pyramid</li>
            <li>Medieval Prison</li>
            <li>Room 057</li>
            <li>The Carnival</li>
          </ul>
        </ul>
        <li>BRo2</li>
      </ul>-->
    </main>
  </body>
</html>
