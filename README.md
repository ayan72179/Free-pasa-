# atom 
Free daily hinge income 
display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1rem;
            margin-bottom: 2rem;
        }
        .stat-card {
            background-color: #1e1e1e;
            padding: 1rem;
            border-radius: 8px;
            text-align: center;
        }
        .stat-card h3 {
            margin-top: 0;
            color: #ff5722;
        }
        .stat-card .value {
            font-size: 2rem;
            font-weight: bold;
        }
        .games-section h2 {
            color: #ff5722;
            border-bottom: 2px solid #ff5722;
            padding-bottom: 0.5rem;
        }
        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1rem;
        }
        .game-card {
            background-color: #1e1e1e;
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.3s;
        }
        .game-card:hover {
            transform: translateY(-5px);
        }
        .game-card img {
            width: 100%;
            height: 120px;
            object-fit: cover;
        }
        .game-card .info {
            padding: 1rem;
        }
        .game-card h3 {
            margin: 0;
        }
        .play-btn {
            display: inline-block;
            background-color: #ff5722;
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            text-decoration: none;
            margin-top: 0.5rem;
            font-weight: bold;
        }
        .time-display {
            background-color: #1e1e1e;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            font-family: monospace;
        }
    </style>
</head>
<body>
    <div class="header">
        <div class="logo">AU Battle</div>
        <div class="user-info">
            <div class="time-display" id="timeDisplay"></div>
            <span>Welcome, <?= htmlspecialchars($user['username']) ?></span>
            <form method="POST" style="display: inline;">
                <input type="hidden" name="action" value="logout">
                <button type="submit" class="logout-btn">Logout</button>
            </form>
        </div>
    </div>
    
    <div class="main-content">
        <div class="sidebar">
            <ul class="sidebar-menu">
                <li><a href="dashboard.php" class="active">Dashboard</a></li>
                <li><a href="#">Play</a></li>
                <li><a href="#">Stats</a></li>
                <li><a href="#">Profile</a></li>
                <li><a href="#">Tournaments</a></li>
                <li><a href="#">Leaderboard</a></li>
            </ul>
        </div>
        
        <div class="content">
            <div class="welcome-banner">
                <h1>Welcome Back, <?= htmlspecialchars($user['username']) ?></h1>
                <p>THOUR | 24 HOUR</p>
                <p>Important Updates</p>
                <a href="#" class="play-btn">Join One</a>
                <span>Completed</span>
            </div>
            
            <div class="stats-cards">
                <div class="stat-card">
                    <h3>Games Played</h3>
                    <div class="value"><?= $user['stats']['games_played'] ?></div>
                </div>
                <div class="stat-card">
                    <h3>Wins</h3>
                    <div class="value"><?= $user['stats']['wins'] ?></div>
                </div>
                <div class="stat-card">
                    <h3>Losses</h3>
                    <div class="value"><?= $user['stats']['losses'] ?></div>
                </div>
            </div>
            
            <div class="games-section">
                <h2>ESPORTS GAMES</h2>
                <div class="games-grid">
