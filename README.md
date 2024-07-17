<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jeu de Ludo</title>
    <style>
        /* Styles pour le plateau de jeu */
        .board {
            display: grid;
            grid-template-columns: repeat(11, 1fr);
            grid-template-rows: repeat(11, 1fr);
            gap: 1px;
            background-color: #f0f0f0;
            border: 1px solid #333;
        }
        .cell {
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 16px;
            background-color: #fff;
            border: 1px solid #ccc;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        .player1 {
            background-color: #ff6347;
        }
        .player2 {
            background-color: #6495ed;
        }
    </style>
</head>
<body>
    <div class="board">
        <!-- Créez les cellules du plateau de jeu ici -->
        <!-- Utilisez des classes comme "cell", "player1", "player2" pour les pions -->
        <!-- Exemple : -->
        <div class="cell"></div>
        <!-- Ajoutez d'autres cellules ici -->
    </div>
    <script>
        // Gestion des déplacements des pions
        const cells = document.querySelectorAll('.cell');
        let currentPlayer = 'player1';

        cells.forEach(cell => {
            cell.addEventListener('click', () => {
                if (!cell.classList.contains('player1') && !cell.classList.contains('player2')) {
                    cell.classList.add(currentPlayer);
                    currentPlayer = (currentPlayer === 'player1') ? 'player2' : 'player1';
                }
            });
        });

        // Règles du jeu (à personnaliser)
        // - Déplacement des pions
        // - Sortie des pions de la base
        // - Capture des pions adverses
        // - Victoire lorsque tous les pions atteignent la case d'arrivée
        // - etc.

        // Ajoutez vos règles spécifiques ici !

        // Animation de survol des cellules (facultatif)
        cells.forEach(cell => {
            cell.addEventListener('mouseenter', () => {
                cell.style.backgroundColor = '#ddd';
            });
            cell.addEventListener('mouseleave', () => {
                cell.style.backgroundColor = '';
            });
        });
    </script>
</body>
</html>
