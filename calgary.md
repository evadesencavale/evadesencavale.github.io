<html>
  <head>
    <title>Calgary</title>
    <style>
     
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
    <script src="https://cdn.jsdelivr.net/npm/tablesorter@2.31.3/dist/js/jquery.tablesorter.combined.min.js"></script>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/tablesorter@2.31.3/dist/css/theme.bootstrap_4.min.css">
    <script>
    $(document).ready(function() {
      console.log("test");
      $("#myTable").tablesorter();
    });
    </script>
    
  </head>
  <body>
    <main>
      The name of this page is: {{ page.name }}
      <h1>Calgary</h1>
      
      <table id="myTable">
        <thead>
          <tr>
            <th class="header">Ville</th>
            <th class="header">Compagnie</th>
            <th class="header">Jeu</th>
            <th class="header">Commentaire</th>
          </tr>
        </thead>
        <tbody>
          {% for item in site.data.calgary_data %}
            <tr>
              <td>{{ item.city }}</td>
              <td>{{ item.company item.url }}</td>
              <td>{{ item.game }}</td>
              <td>{{ item.comment }}</td>
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
