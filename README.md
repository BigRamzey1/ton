<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TON Blockchain Explorer</title>
  <style>
    /* General Body Styling */
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
    }

    /* Header Styling */
    header {
      background-color: #2d89ef;
      color: white;
      padding: 20px 0;
      text-align: center;
    }
    header h1 {
      margin: 0;
    }

    /* Container Styling */
    .container {
      padding: 20px;
      margin-bottom: 50px; /* Prevent footer overlap */
    }

    /* Search Bar Styling */
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

    /* Table Styling */
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

    /* Footer Styling */
    footer {
      text-align: center;
      padding: 10px;
      background-color: #2d89ef;
      color: white;
      position: fixed;
      bottom: 0;
      width: 100%;
    }

    /* Responsive Design */
    @media (max-width: 768px) {
      .search-bar input[type="text"] {
        width: 100%; /* Full width for smaller screens */
      }
      table th, table td {
        font-size: 14px; /* Smaller font size for mobile */
      }
    }
  </style>
</head>
<body>
  <!-- Header Section -->
  <header>
    <h1>TON Blockchain Explorer</h1>
    <h2>Explore transactions, blocks, and wallet addresses</h2>
  </header>

  <!-- Main Content -->
  <div class="container">
    <!-- Search Bar -->
    <form action="/search" method="GET" class="search-bar">
      <label for="search-input" class="visually-hidden">Search:</label>
      <input id="search-input" type="text" name="query" placeholder="Search for transactions, blocks, or wallet addresses">
      <button type="submit">Search</button>
    </form>

    <!-- Table with Transactions -->
    <h2>Latest Transactions</h2>
    <table>
      <caption>List of Latest Transactions</caption>
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
          <td><a href="/transaction/7b90331311de">7b90331311de...</a></td>
          <td>123456</td>
          <td>2025-05-07 02:40:20</td>
          <td>0.25 BTC</td>
        </tr>
        <tr>
          <td><a href="/transaction/9a7f123456de">9a7f123456de...</a></td>
          <td>123457</td>
          <td>2025-05-07 02:38:10</td>
          <td>1.50 BTC</td>
        </tr>
      </tbody>
    </table>
  </div>

  <!-- Footer Section -->
  <footer>
    <p>&copy; 2025 TON Blockchain Explorer</p>
  </footer>
</body>
</html>