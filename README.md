
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Blockchain Explorer</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
    }
    header {
      background-color: #2d89ef;
      color: white;
      padding: 20px 0;
      text-align: center;
    }
    header h1 {
      margin: 0;
    }
    .container {
      padding: 20px;
    }
    .search-bar {
      display: flex;
      justify-content: center;
      margin-bottom: 20px;
    }
    .search-bar input[type="text"] {
      width: 70%;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }
    .search-bar button {
      padding: 10px 20px;
      border: none;
      background-color: #2d89ef;
      color: white;
      cursor: pointer;
      border-radius: 4px;
      margin-left: 10px;
    }
    .search-bar button:hover {
      background-color: #1e5abf;
    }
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 20px;
    }
    table th, table td {
      border: 1px solid #ccc;
      padding: 10px;
      text-align: center;
    }
    table th {
      background-color: #f4f4f4;
    }
    footer {
      text-align: center;
      padding: 10px;
      background-color: #2d89ef;
      color: white;
      position: fixed;
      bottom: 0;
      width: 100%;
    }
  </style>
</head>
<body>
  <header>
    <h1>Blockchain Explorer</h1>
    <p>Explore transactions, blocks, and wallet addresses</p>
  </header>
  <div class="container">
    <div class="search-bar">
      <input type="text" placeholder="Search for transactions, blocks, or wallet addresses">
      <button>Search</button>
    </div>
    <h2>Latest Transactions</h2>
    <table>
      <thead>
        <tr>
          <th>Transaction Hash</th>
          <th>Block</th>
          <th>Timestamp</th>
          <th>Amount</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><a href="#">7b90331311de...</a></td>
          <td>123456</td>
          <td>2025-05-07 02:40:20</td>
          <td>0.25 BTC</td>
        </tr>
        <tr>
          <td><a href="#">9a7f123456de...</a></td>
          <td>123457</td>
          <td>2025-05-07 02:38:10</td>
          <td>1.50 BTC</td>
        </tr>
      </tbody>
    </table>
  </div>
  <footer>
    <p>&copy; 2025 Blockchain Explorer</p>
  </footer>
</body>
</html>