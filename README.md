<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sleek Dashboard</title>
    <style>
        /* Add your CSS here */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(145deg, #1a1a40, #2a2a72);
            color: #f4f4f4;
            background-attachment: fixed;
            background-size: cover;
        }

        header {
            background-color: rgba(0, 0, 0, 0.8);
            color: white;
            padding: 1rem 2rem;
            text-align: center;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.3);
        }

        main {
            padding: 2rem;
            max-width: 900px;
            margin: 0 auto;
        }

        .transaction-summary, .logs {
            background: rgba(255, 255, 255, 0.1);
            margin-bottom: 2rem;
            padding: 1.5rem;
            border-radius: 8px;
            color: #f4f4f4;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.3);
        }

        .transaction-item, .log-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.75rem;
        }

        .transaction-item strong, .log-item strong {
            color: #00b3ff;
        }

        footer {
            background-color: rgba(0, 0, 0, 0.8);
            color: white;
            text-align: center;
            padding: 1rem 0;
            position: fixed;
            bottom: 0;
            width: 100%;
        }

        pre {
            background-color: rgba(0, 0, 0, 0.5);
            padding: 1rem;
            border-radius: 8px;
            overflow-x: auto;
            white-space: pre-wrap;
            word-wrap: break-word;
            color: #00ffbc;
            font-family: "Courier New", Courier, monospace;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to the Dashboard</h1>
    </header>
    <main>
        <section class="transaction-summary">
            <h2>Transaction Summary</h2>
            <div class="transaction-item">
                <span>Transaction ID: 12345</span>
                <strong>View Details</strong>
            </div>
            <div class="transaction-item">
                <span>Transaction ID: 67890</span>
                <strong>View Details</strong>
            </div>
        </section>

        <section class="logs">
            <h2>System Logs</h2>
            <div class="log-item">
                <span>Log #1: Completed successfully</span>
                <strong>Details</strong>
            </div>
            <div class="log-item">
                <span>Log #2: Error detected</span>
                <strong>Details</strong>
            </div>
            <pre>
[2025-05-07 03:42:54] INFO: System initialized
[2025-05-07 03:43:10] ERROR: Missing configuration file
            </pre>
        </section>
    </main>
    <footer>
        <p>&copy; 2025 Sleek Dashboard. All rights reserved.</p>
    </footer>
</body>
</html>