<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BUY and BUY CRYPTO</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #ffffff 0%, #8b5cf6 100%);
            min-height: 100vh;
            color: #333;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        .header {
            text-align: center;
            background: rgba(139, 92, 246, 0.1);
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 30px;
            border: 2px solid #8b5cf6;
            position: relative;
        }
        .header h1 {
            color: #8b5cf6;
            font-size: 2.5em;
            margin-bottom: 10px;
        }
        .nav-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 20px 0;
        }
        .nav-btn {
            background: #8b5cf6;
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.3s ease;
        }
        .nav-btn:hover, .nav-btn.active {
            background: #7c3aed;
            transform: translateY(-2px);
        }
        .page {
            display: none;
            background: rgba(255, 255, 255, 0.9);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(139, 92, 246, 0.3);
            border: 1px solid #8b5cf6;
        }
        .page.active {
            display: block;
        }
        .section {
            background: rgba(139, 92, 246, 0.05);
            margin: 20px 0;
            padding: 20px;
            border-radius: 10px;
            border: 1px solid #8b5cf6;
        }
        .section h3 {
            color: #8b5cf6;
            margin-bottom: 15px;
            border-bottom: 2px solid #8b5cf6;
            padding-bottom: 10px;
        }
        .input-row {
            display: flex;
            gap: 15px;
            margin-bottom: 15px;
            flex-wrap: wrap;
        }
        .input-group {
            flex: 1;
            min-width: 200px;
        }
        .input-group label {
            display: block;
            margin-bottom: 5px;
            color: #8b5cf6;
            font-weight: bold;
        }
        .input-group input, .input-group select {
            width: 100%;
            padding: 10px;
            border: 2px solid #8b5cf6;
            border-radius: 5px;
            background: white;
        }
        .profit-display {
            background: linear-gradient(45deg, #8b5cf6, #7c3aed);
            color: white;
            padding: 15px;
            border-radius: 10px;
            margin: 15px 0;
            text-align: center;
        }
        .bloc-container {
            background: rgba(255, 255, 255, 0.8);
            border: 2px solid #8b5cf6;
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            width: 100%;
        }
        .bloc-title {
            background: #8b5cf6;
            color: white;
            padding: 10px;
            text-align: center;
            border-radius: 5px;
            margin-bottom: 15px;
        }
        .sous-bloc {
            background: rgba(139, 92, 246, 0.1);
            border: 1px solid #8b5cf6;
            border-radius: 8px;
            padding: 15px;
            margin: 10px 0;
        }
        .crypto-selector {
            background: rgba(139, 92, 246, 0.1);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            border: 1px solid #8b5cf6;
        }
        .archive-section {
            background: rgba(139, 92, 246, 0.1);
            padding: 20px;
            border-radius: 10px;
            margin-top: 30px;
            border: 1px solid #8b5cf6;
        }
        .auth-form {
            background: rgba(139, 92, 246, 0.1);
            padding: 30px;
            border-radius: 15px;
            max-width: 400px;
            margin: 0 auto;
            border: 2px solid #8b5cf6;
        }
        .auth-form h3 {
            color: #8b5cf6;
            margin-bottom: 20px;
            text-align: center;
        }
        .form-group {
            margin-bottom: 20px;
        }
        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: #8b5cf6;
            font-weight: bold;
        }
        .form-group input {
            width: 100%;
            padding: 12px;
            border: 2px solid #8b5cf6;
            border-radius: 8px;
            font-size: 16px;
            background: white;
        }
        .btn {
            background: #8b5cf6;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            width: 100%;
            margin: 10px 0;
            transition: background 0.3s ease;
        }
        .btn:hover {
            background: #7c3aed;
        }
        .settings-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #8b5cf6;
            color: white;
            border: none;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            font-size: 24px;
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .settings-btn:hover {
            background: #7c3aed;
        }
        .popup {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 1000;
        }
        .popup-content {
            background: white;
            padding: 30px;
            border-radius: 15px;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            border: 2px solid #8b5cf6;
            text-align: center;
        }
        .user-list {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-top: 20px;
        }
        .user-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 8px;
            border: 1px solid #8b5cf6;
        }
        .user-item button {
            background: #ef4444;
            color: white;
            border: none;
            border-radius: 8px;
            padding: 5px 10px;
            cursor: pointer;
        }
        .user-item button:hover {
            background: #dc2626;
        }
        .hidden {
            display: none;
        }
        .budget-section {
            background-color: #f0f0f0;
            padding: 15px;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        .rates-container {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }
        .rates-container .input-group {
            flex: 1;
            min-width: 150px;
        }
        .stake-amount {
            display: block;
            margin-top: 5px;
            font-size: 0.9em;
            color: #555;
        }
        .price-container {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .price-container input {
            flex: 1;
        }
        .loader {
            border: 4px solid #f3f3f3;
            border-radius: 50%;
            border-top: 4px solid #3498db;
            width: 20px;
            height: 20px;
            animation: spin 2s linear infinite;
            display: none;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .results-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        .results-table th, .results-table td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }
        .results-table th {
            background-color: #f2f2f2;
        }
        .block-header {
            background-color: #e7e7e7;
            font-weight: bold;
        }
        .currency {
            text-align: right;
        }
        .archive-actions {
            display: flex;
            gap: 10px;
            align-items: center;
            margin-top: 20px;
        }
        .calendar-container {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        .calendar-section {
            background: rgba(255, 255, 255, 0.9);
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(139, 92, 246, 0.3);
            border: 1px solid #8b5cf6;
        }
        .calendar-title {
            color: #8b5cf6;
            margin-bottom: 15px;
            text-align: center;
        }
        .calendar-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
        }
        .calendar-cell {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            text-align: center;
        }
        .bullish {
            background-color: #d4edda;
        }
        .bearish {
            background-color: #f8d7da;
        }
        .input-group {
            margin-bottom: 15px;
        }
        .input-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        .input-group input {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: center;
        }
        th {
            background-color: #f2f2f2;
        }
        .language-selector {
            position: absolute;
            top: 20px;
            right: 20px;
            z-index: 100;
        }
        .language-selector select {
            padding: 8px;
            border-radius: 5px;
            border: 1px solid #8b5cf6;
            background-color: white;
        }
        .trading-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            margin-bottom: 20px;
        }
        .trading-cell {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            text-align: center;
            background-color: rgba(139, 92, 246, 0.1);
        }
        .archive-display {
            margin-top: 20px;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            background-color: rgba(139, 92, 246, 0.1);
        }
        .profit-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        .profit-table th, .profit-table td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: center;
        }
        .profit-table th {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🚀 BUY and BUY CRYPTO 🚀</h1>
            <p>Application de Répartition de Mise pour Crypto-monnaies</p>
            <div class="language-selector">
                <select id="language-select" onchange="changeLanguage()">
                    <option value="fr">Français</option>
                    <option value="en">English</option>
                    <option value="es">Español</option>
                    <option value="de">Deutsch</option>
                </select>
            </div>
        </div>
        <div class="nav-buttons">
            <button class="nav-btn active" onclick="showPage('accueil')">🏠 Page d'Accueil</button>
            <button class="nav-btn" onclick="checkAccess('repartition')">📊 Répartition de Mise</button>
            <button class="nav-btn" onclick="checkAccess('calendrier')">📅 Calendrier Crypto</button>
            <button class="nav-btn" onclick="checkAccess('pret-trading')">💰 Prêt Trading Crypto</button>
            <button class="nav-btn" onclick="checkAccess('bilan-profit')">📈 Bilan Profit Trading Crypto</button>
        </div>
        <!-- Page d'Accueil -->
        <div id="accueil" class="page active">
            <h2 style="text-align: center; color: #8b5cf6; margin-bottom: 30px;">Bienvenue sur BUY and BUY CRYPTO</h2>
            <div class="auth-form">
                <h3>🔑 Accès Utilisateur</h3>
                <div class="form-group">
                    <label>Numéro de Téléphone :</label>
                    <input type="tel" id="user-phone" placeholder="Votre numéro de téléphone">
                    <button class="btn" onclick="validateAccess()">Accéder</button>
                </div>
            </div>
        </div>
        <!-- Page Répartition de Mise -->
        <div id="repartition" class="page">
            <h2 style="text-align: center; color: #8b5cf6; margin-bottom: 30px;">Calculateur de Grille Crypto</h2>
            <div class="input-group">
                <label for="crypto-select">Crypto-monnaie :</label>
                <select id="crypto-select"></select>
            </div>
            <div class="input-group">
                <label for="initial-price">Prix Initial (USD) :</label>
                <div class="price-container">
                    <input type="number" id="initial-price" step="any" value="50000">
                    <div class="loader" id="price-loader"></div>
                </div>
            </div>
            <div class="budget-section">
                <div class="input-group">
                    <label for="budget">Budget (USD) :</label>
                    <input type="number" id="budget" step="1" value="300">
                </div>
                <div class="rates-container">
                    <div class="input-group">
                        <label for="rate-1">Taux Mise 1 (%) :</label>
                        <input type="number" id="rate-1" step="0.01" value="3.33">
                        <span class="stake-amount" id="stake-amount-1"></span>
                    </div>
                    <div class="input-group">
                        <label for="rate-2">Taux Mise 2 (%) :</label>
                        <input type="number" id="rate-2" step="0.01" value="6.66">
                        <span class="stake-amount" id="stake-amount-2"></span>
                    </div>
                    <div class="input-group">
                        <label for="rate-3">Taux Mise 3 (%) :</label>
                        <input type="number" id="rate-3" step="0.01" value="10">
                        <span class="stake-amount" id="stake-amount-3"></span>
                    </div>
                    <div class="input-group">
                        <label for="rate-4">Taux Mise 4 (%) :</label>
                        <input type="number" id="rate-4" step="0.01" value="13.33">
                        <span class="stake-amount" id="stake-amount-4"></span>
                    </div>
                </div>
            </div>
            <div class="input-group">
                <label for="grid-interval">Intervalle de Grille (%) :</label>
                <input type="number" id="grid-interval" step="0.01" value="5">
            </div>
            <div class="input-group">
                <label for="trigger-drop">Déclenchement de Baisse (%) :</label>
                <input type="number" id="trigger-drop" step="0.01" value="1">
            </div>
            <div class="input-group">
                <label for="num-blocks">Nombre de Blocs :</label>
                <input type="number" id="num-blocks" value="3">
            </div>
            <button id="generate-grid-btn">Générer la Grille</button>
            <div id="grid-results-container"></div>
            <div class="archive-actions">
                <div class="input-group">
                    <label for="archive-date">Date d'Archivage :</label>
                    <input type="date" id="archive-date">
                </div>
                <button class="btn" onclick="archiveRepartition()">Archiver Répartition</button>
                <button class="btn" onclick="deleteArchive()">Supprimer Archive</button>
            </div>
        </div>
        <!-- Page Calendrier -->
        <div id="calendrier" class="page">
            <h2 style="text-align: center; color: #8b5cf6; margin-bottom: 30px;">📅 Calendrier Crypto</h2>
            <div class="calendar-container">
                <!-- Partie 1: Calendrier Haussier et Baissier -->
                <div class="calendar-section">
                    <h3 class="calendar-title">Calendrier Haussier et Baissier (12 Mois)</h3>
                    <div class="input-group">
                        <label for="calendar-start-date">Date de Début du Calendrier :</label>
                        <input type="date" id="calendar-start-date" onchange="generateCalendar()">
                    </div>
                    <div class="calendar-grid" id="calendar-grid"></div>
                </div>
                <!-- Partie 2: Calendrier 3 x 6 Mois Haussier -->
                <div class="calendar-section">
                    <h3 class="calendar-title">Calendrier 3 x 6 Mois Haussier</h3>
                    <p style="text-align: center; color: #8b5cf6; margin: 20px 0;">
                        Périodes de 6 mois consécutifs avec tendance haussière prononcée
                    </p>
                    <div class="input-group">
                        <label for="days-input">Veuillez insérer entre 90 jour et 120 :</label>
                        <input type="number" id="days-input" value="90">
                    </div>
                    <div class="input-group">
                        <label for="crypto-price">Mettez point Crypto :</label>
                        <input type="number" id="crypto-price" value="95000">
                    </div>
                    <table id="bullish-calendar">
                        <thead>
                            <tr>
                                <th>REF</th>
                                <th>DATE PROBABLE</th>
                                <th>Tx Dégressif</th>
                                <th>Point Haussier Crypto</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>1</td>
                                <td><input type="date" id="date1" onchange="updateDates()"></td>
                                <td rowspan="2" id="rate-column">11</td>
                                <td rowspan="3" id="crypto-price-column"></td>
                            </tr>
                            <tr>
                                <td>2</td>
                                <td><input type="date" id="date2" readonly></td>
                            </tr>
                            <tr>
                                <td>3</td>
                                <td><input type="date" id="date3" readonly></td>
                                <td id="cumulative-rate1">22</td>
                            </tr>
                            <tr>
                                <td>4</td>
                                <td><input type="date" id="date4" readonly></td>
                                <td rowspan="2">11</td>
                                <td rowspan="3" id="crypto-price-column2"></td>
                            </tr>
                            <tr>
                                <td>5</td>
                                <td><input type="date" id="date5" readonly></td>
                            </tr>
                            <tr>
                                <td>6</td>
                                <td><input type="date" id="date6" readonly></td>
                                <td id="cumulative-rate2">22</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
        <!-- Page Prêt Trading Crypto -->
        <div id="pret-trading" class="page">
            <h2 style="text-align: center; color: #8b5cf6; margin-bottom: 30px;">💰 Prêt Trading Crypto</h2>
            <div class="trading-grid">
                <div class="trading-cell">
                    <label for="collateral-budget">Budget de Garantie (USDT) :</label>
                    <input type="number" id="collateral-budget" value="250" onchange="updateAllCalculations()">
                </div>
                <div class="trading-cell">
                    <label for="loan-ratio">Ratio Taux d'Emprunt Conseillé (%) :</label>
                    <input type="number" id="loan-ratio" value="80" onchange="updateAllCalculations()">
                </div>
                <div class="trading-cell">
                    <label for="loan-amount">Montant à Emprunter Conseillé (USDT) :</label>
                    <input type="number" id="loan-amount" readonly>
                </div>
                <div class="trading-cell">
                    <label for="debt-ratio">Debt Ratio (%) :</label>
                    <input type="number" id="debt-ratio" readonly>
                </div>
                <div class="trading-cell">
                    <label for="interest-rate">Taux d'Intérêt du Prêt par Jour (%) :</label>
                    <input type="number" id="interest-rate" value="0.017" onchange="updateAllCalculations()">
                </div>
                <div class="trading-cell">
                    <label for="loan-duration">Durée du Prêt (Jours) :</label>
                    <input type="number" id="loan-duration" value="28" onchange="updateAllCalculations()">
                </div>
                <div class="trading-cell">
                    <label for="total-interest">Total Intérêt à Payer (%) :</label>
                    <input type="number" id="total-interest" readonly>
                </div>
                <div class="trading-cell">
                    <label for="total-repayment">Total à Rembourser (USDT) :</label>
                    <input type="number" id="total-repayment" readonly>
                </div>
            </div>
            <div class="archive-actions">
                <div class="input-group">
                    <label for="loan-archive-date">Date d'Archivage :</label>
                    <input type="date" id="loan-archive-date">
                </div>
                <button class="btn" onclick="archiveLoan()">Archiver Prêt Trading</button>
                <div class="input-group">
                    <label for="loan-archive-select">Sélectionner une Archive :</label>
                    <select id="loan-archive-select" onchange="displaySelectedArchive()">
                        <option value="">-- Sélectionner une date --</option>
                    </select>
                </div>
                <button class="btn" onclick="deleteLoanArchive()">Supprimer Archive</button>
            </div>
            <div id="archive-display" class="archive-display hidden">
                <h3>Données de l'archive sélectionnée</h3>
                <div class="trading-grid">
                    <div class="trading-cell">
                        <label>Budget de Garantie (USDT) :</label>
                        <input type="number" id="display-collateral-budget" readonly>
                    </div>
                    <div class="trading-cell">
                        <label>Ratio Taux d'Emprunt (%) :</label>
                        <input type="number" id="display-loan-ratio" readonly>
                    </div>
                    <div class="trading-cell">
                        <label>Montant à Emprunter (USDT) :</label>
                        <input type="number" id="display-loan-amount" readonly>
                    </div>
                    <div class="trading-cell">
                        <label>Debt Ratio (%) :</label>
                        <input type="number" id="display-debt-ratio" readonly>
                    </div>
                    <div class="trading-cell">
                        <label>Taux d'Intérêt par Jour (%) :</label>
                        <input type="number" id="display-interest-rate" readonly>
                    </div>
                    <div class="trading-cell">
                        <label>Durée du Prêt (Jours) :</label>
                        <input type="number" id="display-loan-duration" readonly>
                    </div>
                    <div class="trading-cell">
                        <label>Total Intérêt à Payer (%) :</label>
                        <input type="number" id="display-total-interest" readonly>
                    </div>
                    <div class="trading-cell">
                        <label>Total à Rembourser (USDT) :</label>
                        <input type="number" id="display-total-repayment" readonly>
                    </div>
                </div>
            </div>
        </div>
        <!-- Page Bilan Profit Trading Crypto -->
        <div id="bilan-profit" class="page">
            <h2 style="text-align: center; color: #8b5cf6; margin-bottom: 30px;">📈 Bilan Profit Trading Crypto</h2>
            <div class="trading-grid">
                <div class="trading-cell">
                    <label for="total-profit">Total Profit (USDT) :</label>
                    <input type="number" id="total-profit" readonly>
                </div>
                <div class="trading-cell">
                    <label for="profit-rate">Taux Profit (%) :</label>
                    <input type="number" id="profit-rate" readonly>
                </div>
                <div class="trading-cell">
                    <label for="initial-capital">Capital Initial (USDT) :</label>
                    <input type="number" id="initial-capital" value="300" onchange="updateProfitRate()">
                    <button class="btn" onclick="clearAdjustableCells()">Supprimer Données Saisies</button>
                </div>
            </div>
            <table class="profit-table">
                <thead>
                    <tr>
                        <th>N°</th>
                        <th>Date Début</th>
                        <th>Date Fin</th>
                        <th>Budget Début (USDT)</th>
                        <th>Budget Fin (USDT)</th>
                        <th>Profit (USDT)</th>
                        <th>Taux Profit (%)</th>
                    </tr>
                </thead>
                <tbody id="profit-table-body">
                    <!-- Les lignes seront ajoutées dynamiquement -->
                </tbody>
            </table>
            <button class="btn" onclick="addNewRow()">Ajouter une Ligne</button>
        </div>
        <!-- Popup pour le code secret de l'administrateur -->
        <div id="secret-code-popup" class="popup">
            <div class="popup-content">
                <h3>Code Secret Administrateur</h3>
                <div class="form-group">
                    <label>Code Secret :</label>
                    <input type="password" id="admin-secret" placeholder="Entrez le code secret">
                </div>
                <button class="btn" onclick="checkAdminAccess()">Accéder</button>
            </div>
        </div>
        <!-- Page Paramètres -->
        <div id="parametres" class="page">
            <h2 style="text-align: center; color: #8b5cf6; margin-bottom: 30px;">⚙️ Paramètres Administrateur</h2>
            <div class="auth-form">
                <h3>Ajouter un Utilisateur</h3>
                <div class="form-group">
                    <label>Nom et Prénom :</label>
                    <input type="text" id="admin-user-name" placeholder="Nom de l'utilisateur">
                </div>
                <div class="form-group">
                    <label>Numéro de Téléphone :</label>
                    <input type="tel" id="admin-user-phone" placeholder="Numéro de téléphone">
                </div>
                <button class="btn" onclick="addUser()">Ajouter Utilisateur</button>
            </div>
            <div class="user-list" id="admin-user-list">
                <!-- Liste des utilisateurs -->
            </div>
        </div>
        <button class="settings-btn" onclick="showAdminSecretPopup()">⚙️</button>
    </div>
    <!-- Popup pour messages -->
    <div id="message-popup" class="popup">
        <div class="popup-content">
            <h3 id="popup-title">Information</h3>
            <p id="popup-message">Message</p>
            <button class="btn" onclick="closeMessagePopup()">Fermer</button>
        </div>
    </div>
    <script>
        // Variables globales
        let users = JSON.parse(localStorage.getItem('cryptoUsers')) || [
            { name: "John Gobolo", phone: "2250586214172" }
        ];
        let archives = JSON.parse(localStorage.getItem('cryptoArchives')) || [];
        let loanArchives = JSON.parse(localStorage.getItem('loanArchives')) || [];
        let profitData = JSON.parse(localStorage.getItem('profitData')) || [];
        let isAuthenticated = false;
        const adminSecretCode = "Gob19*20";
        const CRYPTO_LIST = [
            { name: 'Bitcoin', symbol: 'BTC', id: 'bitcoin' },
            { name: 'Ethereum', symbol: 'ETH', id: 'ethereum' },
            { name: 'Cardano', symbol: 'ADA', id: 'cardano' },
            { name: 'Solana', symbol: 'SOL', id: 'solana' },
            { name: 'Ripple', symbol: 'XRP', id: 'ripple' },
            { name: 'Dogecoin', symbol: 'DOGE', id: 'dogecoin' },
            { name: 'Polkadot', symbol: 'DOT', id: 'polkadot-new' },
            { name: 'Avalanche', symbol: 'AVAX', id: 'avalanche-2' },
            { name: 'Polygon', symbol: 'MATIC', id: 'matic-network' },
            { name: 'Litecoin', symbol: 'LTC', id: 'litecoin' },
            { name: 'LISTE XSTOCKS', symbol: 'XSTOCKS', id: 'xstocks' },
            { name: 'CRCLX', symbol: 'CRCLX/USDT', id: 'crclx' },
            { name: 'AAPLX', symbol: 'AAPLX/USDT', id: 'aaplx' },
            { name: 'COINX', symbol: 'COINX/USDT', id: 'coinx' },
            { name: 'TSLAX', symbol: 'TSLAX/USDT', id: 'tslax' },
            { name: 'NVDAX', symbol: 'NVDAX/USDT', id: 'nvda' },
            { name: 'AMZNX', symbol: 'AMZNX/USDT', id: 'amznx' },
            { name: 'MSTRX', symbol: 'MSTRX/USDT', id: 'mstrx' },
            { name: 'HOODX', symbol: 'HOODX/USDT', id: 'hoodx' },
            { name: 'GOOGLX', symbol: 'GOOGLX/USDT', id: 'googlx' },
            { name: 'QQQX', symbol: 'QQQX/USDT', id: 'qqqx' },
            { name: 'SPYX', symbol: 'SPYX/USDT', id: 'spy' },
            { name: 'METAX', symbol: 'METAX/USDT', id: 'meta' }
        ];

        function populateCryptoDropdown() {
            const select = document.getElementById('crypto-select');
            CRYPTO_LIST.forEach(crypto => {
                const option = document.createElement('option');
                option.value = crypto.id;
                option.textContent = `${crypto.name} (${crypto.symbol})`;
                select.appendChild(option);
            });
        }

        async function fetchCryptoPrice(cryptoId) {
            const loader = document.getElementById('price-loader');
            const priceInput = document.getElementById('initial-price');
            try {
                loader.style.display = 'block';
                const response = await fetch(`https://api.coingecko.com/api/v3/simple/price?ids=${cryptoId}&vs_currencies=usd`);
                if (!response.ok) {
                    throw new Error('Network response was not ok');
                }
                const data = await response.json();
                if (data[cryptoId] && data[cryptoId].usd) {
                    priceInput.value = data[cryptoId].usd;
                    priceInput.dispatchEvent(new Event('input'));
                }
            } catch (error) {
                console.error('Failed to fetch crypto price:', error);
            } finally {
                loader.style.display = 'none';
            }
        }

        function updateStakeAmounts() {
            const budget = parseFloat(document.getElementById('budget').value) || 0;
            for (let i = 1; i <= 4; i++) {
                const rate = parseFloat(document.getElementById(`rate-${i}`).value) || 0;
                const amount = budget * (rate / 100);
                const amountElem = document.getElementById(`stake-amount-${i}`);
                if (amountElem) {
                    amountElem.textContent = `Mise: $${amount.toFixed(2)}`;
                }
            }
        }

        function generateGrid() {
            const initialPrice = parseFloat(document.getElementById('initial-price').value);
            const gridInterval = parseFloat(document.getElementById('grid-interval').value) / 100;
            const triggerDrop = parseFloat(document.getElementById('trigger-drop').value) / 100;
            const numBlocks = parseInt(document.getElementById('num-blocks').value, 10);
            const resultsContainer = document.getElementById('grid-results-container');
            const budget = parseFloat(document.getElementById('budget').value);
            const rate1 = parseFloat(document.getElementById('rate-1').value) / 100;
            const rate2 = parseFloat(document.getElementById('rate-2').value) / 100;
            const rate3 = parseFloat(document.getElementById('rate-3').value) / 100;
            const rate4 = parseFloat(document.getElementById('rate-4').value) / 100;
            const newStakesRates = [rate1, rate2, rate3, rate4];
            const allInputs = [initialPrice, gridInterval, triggerDrop, numBlocks, budget, ...newStakesRates];
            if (allInputs.some(input => isNaN(input) || input < 0) || numBlocks < 1) {
                resultsContainer.innerHTML = `<p style="color: red; text-align: center;">Veuillez entrer des valeurs numériques valides et positives pour tous les champs.</p>`;
                return;
            }
            let currentTriggerPrice = initialPrice * (1 - triggerDrop);
            const blocks = [];
            const stakes = newStakesRates.map(rate => budget * rate);
            for (let i = 0; i < numBlocks; i++) {
                const block = {
                    blockNumber: i + 1,
                    subBlocks: []
                };
                let priceForBlock = (i === 0) ? initialPrice : blocks[i-1].subBlocks[3].lowerPrice;
                currentTriggerPrice = priceForBlock * (1 - triggerDrop);
                for (let j = 0; j < 4; j++) {
                    const lowerPrice = currentTriggerPrice * (1 - gridInterval);
                    const upperPrice = currentTriggerPrice * (1 + gridInterval);
                    block.subBlocks.push({
                        triggerPrice: currentTriggerPrice,
                        lowerPrice: lowerPrice,
                        upperPrice: upperPrice,
                        stake: stakes[j]
                    });
                    currentTriggerPrice = lowerPrice * (1-triggerDrop);
                }
                blocks.push(block);
            }
            renderTable(blocks, resultsContainer);
        }

        function renderTable(blocks, container) {
            container.innerHTML = '';
            blocks.forEach(block => {
                const table = document.createElement('table');
                table.classList.add('results-table');
                const tableHead = document.createElement('thead');
                const headerRow = document.createElement('tr');
                const headerCell = document.createElement('th');
                headerCell.colSpan = 4;
                headerCell.textContent = `Bloc ${block.blockNumber}`;
                headerCell.classList.add('block-header');
                headerRow.appendChild(headerCell);
                tableHead.appendChild(headerRow);
                table.appendChild(tableHead);
                const tableBody = document.createElement('tbody');
                block.subBlocks.forEach((subBlock, index) => {
                    const row = document.createElement('tr');
                    const triggerCell = document.createElement('td');
                    triggerCell.innerHTML = `Déclenchement: <br><b>$${subBlock.triggerPrice.toFixed(4)}</b>`;
                    row.appendChild(triggerCell);
                    const lowerCell = document.createElement('td');
                    lowerCell.innerHTML = `Achat (Limite Basse): <br><b>$${subBlock.lowerPrice.toFixed(4)}</b>`;
                    row.appendChild(lowerCell);
                    const upperCell = document.createElement('td');
                    upperCell.innerHTML = `Vente (Limite Haute): <br><b>$${subBlock.upperPrice.toFixed(4)}</b>`;
                    row.appendChild(upperCell);
                    const stakeCell = document.createElement('td');
                    stakeCell.innerHTML = `Mise: <br><b>$${subBlock.stake.toFixed(2)}</b>`;
                    stakeCell.classList.add('currency');
                    row.appendChild(stakeCell);
                    tableBody.appendChild(row);
                });
                table.appendChild(tableBody);
                container.appendChild(table);
            });
        }

        function archiveRepartition() {
            const date = document.getElementById('archive-date').value;
            if (!date) {
                showMessagePopup('Erreur', 'Veuillez sélectionner une date d\'archivage.');
                return;
            }
            const archive = {
                date,
                content: document.getElementById('grid-results-container').innerHTML
            };
            archives.push(archive);
            localStorage.setItem('cryptoArchives', JSON.stringify(archives));
            showMessagePopup('Archive Réussie', 'La répartition a été archivée avec succès.');
        }

        function deleteArchive() {
            archives = [];
            localStorage.setItem('cryptoArchives', JSON.stringify(archives));
            showMessagePopup('Archives Supprimées', 'Toutes les archives ont été supprimées avec succès.');
        }

        function generateCalendar() {
            const startDateInput = document.getElementById('calendar-start-date').value;
            if (!startDateInput) {
                alert("Veuillez sélectionner une date de début.");
                return;
            }
            const startDate = new Date(startDateInput);
            const calendarGrid = document.getElementById('calendar-grid');
            calendarGrid.innerHTML = '';
            for (let month = 0; month < 12; month++) {
                const monthStart = new Date(startDate);
                monthStart.setMonth(startDate.getMonth() + month);
                const bullishStart = new Date(monthStart);
                const bullishEnd = new Date(bullishStart);
                bullishEnd.setDate(bullishStart.getDate() + 6);
                const bearishStart = new Date(bullishEnd);
                const bearishEnd = new Date(bullishStart);
                bearishEnd.setDate(bullishStart.getDate() + 13);
                const monthDiv = document.createElement('div');
                monthDiv.className = 'calendar-month';
                const monthTitle = document.createElement('h3');
                monthTitle.textContent = `Mois ${month + 1}`;
                monthDiv.appendChild(monthTitle);
                const bullishDiv = document.createElement('div');
                bullishDiv.className = 'calendar-cell bullish';
                bullishDiv.innerHTML = `
                    <div>Date Haussière Début: ${bullishStart.toLocaleDateString()}</div>
                    <div>Date Haussière Fin: ${bullishEnd.toLocaleDateString()}</div>
                `;
                monthDiv.appendChild(bullishDiv);
                const bearishDiv = document.createElement('div');
                bearishDiv.className = 'calendar-cell bearish';
                bearishDiv.innerHTML = `
                    <div>Date Baissière Début: ${bearishStart.toLocaleDateString()}</div>
                    <div>Date Baissière Fin: ${bearishEnd.toLocaleDateString()}</div>
                `;
                monthDiv.appendChild(bearishDiv);
                calendarGrid.appendChild(monthDiv);
            }
        }

        function updateDates() {
            const daysInput = parseInt(document.getElementById('days-input').value) || 90;
            const cryptoPrice = parseFloat(document.getElementById('crypto-price').value) || 95000;
            const date1Input = document.getElementById('date1');
            const date1 = new Date(date1Input.value);

            if (!date1Input.value) {
                alert("Veuillez sélectionner une date de début.");
                return;
            }

            const date2Input = document.getElementById('date2');
            const date3Input = document.getElementById('date3');
            const date4Input = document.getElementById('date4');
            const date5Input = document.getElementById('date5');
            const date6Input = document.getElementById('date6');

            const date2 = new Date(date1);
            date2.setDate(date1.getDate() + daysInput);
            date2Input.valueAsDate = date2;

            const date3 = new Date(date2);
            date3.setDate(date2.getDate() + daysInput);
            date3Input.valueAsDate = date3;

            const date4 = new Date(date3);
            date4.setDate(date3.getDate() + daysInput);
            date4Input.valueAsDate = date4;

            const date5 = new Date(date4);
            date5.setDate(date4.getDate() + daysInput);
            date5Input.valueAsDate = date5;

            const date6 = new Date(date5);
            date6.setDate(date5.getDate() + daysInput);
            date6Input.valueAsDate = date6;

            updateCryptoPrices(cryptoPrice);
        }

        function updateCryptoPrices(initialPrice) {
            const rate = 0.22;
            const cryptoPriceColumn = document.getElementById('crypto-price-column');
            const cryptoPriceColumn2 = document.getElementById('crypto-price-column2');

            const price1 = initialPrice * (1 + rate);
            const price2 = price1 * (1 + rate);
            const price3 = price2 * (1 + rate);

            cryptoPriceColumn.innerHTML = `
                <div>${initialPrice.toFixed(2)}</div>
                <div>${price1.toFixed(2)}</div>
            `;

            cryptoPriceColumn2.innerHTML = `
                <div>${price2.toFixed(2)}</div>
                <div>${price3.toFixed(2)}</div>
            `;
        }

        function updateLoanAmount() {
            const collateralBudget = parseFloat(document.getElementById('collateral-budget').value) || 0;
            const loanRatio = parseFloat(document.getElementById('loan-ratio').value) || 0;
            const loanAmount = collateralBudget * (loanRatio / 100);
            document.getElementById('loan-amount').value = loanAmount.toFixed(2);
            updateDebtRatio();
        }

        function updateDebtRatio() {
            const collateralBudget = parseFloat(document.getElementById('collateral-budget').value) || 0;
            const loanAmount = parseFloat(document.getElementById('loan-amount').value) || 0;
            const debtRatio = (loanAmount / (collateralBudget + loanAmount)) * 100;
            document.getElementById('debt-ratio').value = debtRatio.toFixed(2);
        }

        function updateTotalInterest() {
            const loanAmount = parseFloat(document.getElementById('loan-amount').value) || 0;
            const interestRate = parseFloat(document.getElementById('interest-rate').value) || 0;
            const loanDuration = parseFloat(document.getElementById('loan-duration').value) || 0;
            const totalInterest = loanAmount * (interestRate / 100) * loanDuration;
            document.getElementById('total-interest').value = totalInterest.toFixed(4);
            updateTotalRepayment();
        }

        function updateTotalRepayment() {
            const loanAmount = parseFloat(document.getElementById('loan-amount').value) || 0;
            const totalInterest = parseFloat(document.getElementById('total-interest').value) || 0;
            const totalRepayment = loanAmount + totalInterest;
            document.getElementById('total-repayment').value = totalRepayment.toFixed(4);
        }

        function updateAllCalculations() {
            updateLoanAmount();
            updateTotalInterest();
        }

        function archiveLoan() {
            const date = document.getElementById('loan-archive-date').value;
            if (!date) {
                showMessagePopup('Erreur', 'Veuillez sélectionner une date d\'archivage.');
                return;
            }
            const loanData = {
                date,
                collateralBudget: document.getElementById('collateral-budget').value,
                loanRatio: document.getElementById('loan-ratio').value,
                loanAmount: document.getElementById('loan-amount').value,
                debtRatio: document.getElementById('debt-ratio').value,
                interestRate: document.getElementById('interest-rate').value,
                loanDuration: document.getElementById('loan-duration').value,
                totalInterest: document.getElementById('total-interest').value,
                totalRepayment: document.getElementById('total-repayment').value
            };
            loanArchives.push(loanData);
            localStorage.setItem('loanArchives', JSON.stringify(loanArchives));
            populateLoanArchiveSelect();
            showMessagePopup('Archive Réussie', 'Le prêt trading a été archivé avec succès.');
        }

        function deleteLoanArchive() {
            loanArchives = [];
            localStorage.setItem('loanArchives', JSON.stringify(loanArchives));
            populateLoanArchiveSelect();
            showMessagePopup('Archives Supprimées', 'Toutes les archives de prêt ont été supprimées avec succès.');
        }

        function populateLoanArchiveSelect() {
            const select = document.getElementById('loan-archive-select');
            select.innerHTML = '<option value="">-- Sélectionner une date --</option>';
            loanArchives.forEach((archive, index) => {
                const option = document.createElement('option');
                option.value = index;
                option.textContent = archive.date;
                select.appendChild(option);
            });
        }

        function displaySelectedArchive() {
            const select = document.getElementById('loan-archive-select');
            const selectedIndex = select.value;
            if (selectedIndex === "") {
                document.getElementById('archive-display').classList.add('hidden');
                return;
            }
            const archive = loanArchives[selectedIndex];
            document.getElementById('display-collateral-budget').value = archive.collateralBudget;
            document.getElementById('display-loan-ratio').value = archive.loanRatio;
            document.getElementById('display-loan-amount').value = archive.loanAmount;
            document.getElementById('display-debt-ratio').value = archive.debtRatio;
            document.getElementById('display-interest-rate').value = archive.interestRate;
            document.getElementById('display-loan-duration').value = archive.loanDuration;
            document.getElementById('display-total-interest').value = archive.totalInterest;
            document.getElementById('display-total-repayment').value = archive.totalRepayment;
            document.getElementById('archive-display').classList.remove('hidden');
        }

        function addNewRow() {
            const tableBody = document.getElementById('profit-table-body');
            const rowCount = tableBody.rows.length;
            const newRow = document.createElement('tr');

            newRow.innerHTML = `
                <td>${rowCount + 1}</td>
                <td><input type="date" onchange="updateProfitCalculations()"></td>
                <td><input type="date" onchange="updateProfitCalculations()"></td>
                <td><input type="number" value="300" onchange="updateProfitCalculations()"></td>
                <td><input type="number" value="450" onchange="updateProfitCalculations()"></td>
                <td><input type="number" readonly></td>
                <td><input type="number" readonly></td>
            `;

            tableBody.appendChild(newRow);
            updateProfitCalculations();
        }

        function updateProfitCalculations() {
            let totalProfit = 0;
            const initialCapital = parseFloat(document.getElementById('initial-capital').value) || 0;
            const rows = document.querySelectorAll('#profit-table-body tr');

            rows.forEach(row => {
                const startBudget = parseFloat(row.cells[3].querySelector('input').value) || 0;
                const endBudget = parseFloat(row.cells[4].querySelector('input').value) || 0;
                const profit = endBudget - startBudget;
                const profitRate = (profit / startBudget) * 100;

                row.cells[5].querySelector('input').value = profit.toFixed(2);
                row.cells[6].querySelector('input').value = profitRate.toFixed(2);

                totalProfit += profit;
            });

            document.getElementById('total-profit').value = totalProfit.toFixed(2);
            updateProfitRate(initialCapital);
        }

        function updateProfitRate(initialCapital) {
            const totalProfit = parseFloat(document.getElementById('total-profit').value) || 0;
            const profitRate = (totalProfit / initialCapital) * 100;
            document.getElementById('profit-rate').value = profitRate.toFixed(2);
        }

        function clearAdjustableCells() {
            const rows = document.querySelectorAll('#profit-table-body tr');
            rows.forEach(row => {
                const inputs = row.querySelectorAll('input:not([readonly])');
                inputs.forEach(input => {
                    input.value = '';
                });
            });
            document.getElementById('total-profit').value = '0.00';
            document.getElementById('profit-rate').value = '0.00';
        }

        function changeLanguage() {
            const language = document.getElementById('language-select').value;
            alert(`Langue changée en : ${language}`);
            // Ajoutez ici la logique pour changer la langue de l'application
        }

        // Navigation entre pages
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
            document.querySelectorAll('.nav-btn').forEach(btn => btn.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
        }

        function checkAccess(pageId) {
            if (isAuthenticated) {
                showPage(pageId);
            } else {
                showMessagePopup('Accès Refusé', 'Veuillez entrer votre numéro de téléphone pour accéder à cette page.');
            }
        }

        // Fonction pour valider l'accès
        function validateAccess() {
            const phone = document.getElementById('user-phone').value;
            if (!phone) {
                showMessagePopup('Erreur', 'Veuillez saisir votre numéro de téléphone.');
                return;
            }
            const userExists = users.some(user => user.phone === phone);
            if (!userExists) {
                showMessagePopup('Accès Refusé', 'Ce numéro de téléphone n\'est pas enregistré.');
                return;
            }
            isAuthenticated = true;
            showMessagePopup('Accès Autorisé', 'Vous avez accès aux autres pages du site.');
        }

        // Fonction pour afficher le popup du code secret administrateur
        function showAdminSecretPopup() {
            document.getElementById('secret-code-popup').style.display = 'block';
        }

        // Fonction pour vérifier l'accès administrateur
        function checkAdminAccess() {
            const secretCode = document.getElementById('admin-secret').value;
            if (secretCode === adminSecretCode) {
                document.getElementById('secret-code-popup').style.display = 'none';
                showPage('parametres');
            } else {
                showMessagePopup('Accès Refusé', 'Code secret incorrect.');
            }
        }

        // Fonction pour ajouter un utilisateur
        function addUser() {
            const name = document.getElementById('admin-user-name').value;
            const phone = document.getElementById('admin-user-phone').value;
            if (!name || !phone) {
                showMessagePopup('Erreur', 'Veuillez remplir tous les champs obligatoires.');
                return;
            }
            const newUser = { name, phone };
            users.push(newUser);
            localStorage.setItem('cryptoUsers', JSON.stringify(users));
            showMessagePopup('Utilisateur Ajouté', 'L\'utilisateur a été ajouté avec succès !');
            updateAdminUserList();
        }

        // Fonction pour afficher la liste des utilisateurs dans la section admin
        function updateAdminUserList() {
            const userListElement = document.getElementById('admin-user-list');
            userListElement.innerHTML = '';
            users.forEach(user => {
                const userItem = document.createElement('div');
                userItem.className = 'user-item';
                userItem.innerHTML = `
                    <span>${user.name} (${user.phone})</span>
                    <button onclick="deleteUser('${user.phone}')">Supprimer</button>
                `;
                userListElement.appendChild(userItem);
            });
        }

        // Fonction pour supprimer un utilisateur
        function deleteUser(phone) {
            users = users.filter(user => user.phone !== phone);
            localStorage.setItem('cryptoUsers', JSON.stringify(users));
            updateAdminUserList();
            showMessagePopup('Utilisateur Supprimé', 'L\'utilisateur a été supprimé avec succès.');
        }

        // Fonction pour afficher un popup de message
        function showMessagePopup(title, message) {
            document.getElementById('popup-title').textContent = title;
            document.getElementById('popup-message').textContent = message;
            document.getElementById('message-popup').style.display = 'block';
        }

        // Fonction pour fermer le popup de message
        function closeMessagePopup() {
            document.getElementById('message-popup').style.display = 'none';
        }

        document.addEventListener('DOMContentLoaded', () => {
            populateCryptoDropdown();
            const cryptoSelect = document.getElementById('crypto-select');
            cryptoSelect.addEventListener('change', (e) => {
                fetchCryptoPrice(e.target.value);
            });
            const inputs = document.querySelectorAll('#repartition input');
            inputs.forEach(input => {
                input.addEventListener('input', () => {
                    updateStakeAmounts();
                    generateGrid();
                });
            });
            document.getElementById('generate-grid-btn').addEventListener('click', generateGrid);
            // Initialize calendar with today's date
            const today = new Date();
            document.getElementById('calendar-start-date').valueAsDate = today;
            document.getElementById('loan-archive-date').valueAsDate = today;
            generateCalendar();
            fetchCryptoPrice(cryptoSelect.value);
            updateStakeAmounts();
            updateAdminUserList();
            populateLoanArchiveSelect();
        });
    </script>
</body>
</html>


