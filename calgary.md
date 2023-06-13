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
      
      <div>
        <h2>Proposition</h2>
        <p>En assumant qu'on arrive le jeudi soir et qu'on repart le mardi, ça nous donnerait 4 jours de jeux. Si on s'installe vendredi matin, on pourrait y'aller avec un genre de:</p>
        <ul>
          <li>Vendredi après-midi/soir: Amaze Calgary</li>
          <li>Samedi matin: The Locked Room (SL)</li>
          <li>Samedi après-midi/soir: Arcadia Adventures</li>
          <li>Dimanche toute la journée: Confined</li>
          <li>Lundi matin: Escape Ops</li>
          <li>Lundi après-midi/soir: Escape 60</li>
        </ul>
        <p>En regardant l'horaire de plus près plus tard, on verra si on peut caser Get Outta Here et/ou la nouvelle succursale de Escape 60. Y'a toujours la possibilité de ne pas être en même temps à chaque succursale si on veut aller faire un jeu unique par exemple.</p>
      </div>
      
      {% assign uniqueCompanies = site.data.calgary_data | map: 'company' | uniq %}
      
      {% for company in uniqueCompanies %}
        {% for item in site.data.calgary_data %}
          {% if item.company == company %}
            {% assign companyUrl = item.companyUrl %}
            {% assign companyComment = item.companyComment %}
          {% endif %}
        {% endfor %}
        <h2><a href="{{ companyUrl }}" target="_blank">{{ company }}</a></h2>
        <span>Commentaire: {{ companyComment }}</span>
        <table class="myTable">
          <thead>
            <tr>
              <!-- <th class="header">Compagnie</th> -->
              <th class="header" style="min-width: 25%">Jeu</th>
              <th class="header">Commentaire</th>
              <th class="header">Intérêt</th>
            </tr>
          </thead>
          <tbody>
            {% for item in site.data.calgary_data %}
              {% if item.company == company %}
                <tr>
                  <!-- <td>{{ item.company }}</td> -->
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
