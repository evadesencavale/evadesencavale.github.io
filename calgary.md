<html>
  <head>
    <title>Calgary</title>
    <style>
      .wrapper {
        max-width: 90%;
        margin-right: auto;
        margin-left: auto;
        padding-right: 30px;
        padding-left: 30px;
      }
      
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
      $(".myTable").tablesorter();
    });
    </script>
    
  </head>
  <body>
    <main>
      <h1>Calgary</h1>
      
      {% assign uniqueCompanies = site.data.calgary_data | map: 'company' | uniq %}
      
      {% for company in uniqueCompanies %}
        <h2><a href="{{ item.companyUrl }}">{{ company }}</a></h2>
        <table class="myTable">
          <thead>
            <tr>
              <th class="header">Compagnie</th>
              <th class="header">Jeu</th>
              <th class="header">Commentaire</th>
              <th class="header">Intérêt</th>
            </tr>
          </thead>
          <tbody>
            {% for item in site.data.calgary_data %}
              {% if item.company == company %}
                <tr>
                  <td>{{ item.company }}</td>
                  <td>{{ item.game }}</td>
                  <td>{{ item.comment }}</td>
                  <td>{{ item.interest }}</td>
                </tr>
              {% endif %}
            {% endfor %}
          </tbody>
        </table>
      {% endfor %}

    </main>
  </body>
</html>
