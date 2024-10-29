---
layout: page
permalink: /leaderboard
permalink_name: /leader board
title: Leaderboard
---
<style>
    #leaderboard {
        margin: 20px 0;
    }

    #leaderboard-entries {
        width: 50%;
        border-collapse: collapse;
    }

    #leaderboard-entries th, #leaderboard-entries td {
        padding: 6px; /* Increased padding for better spacing */
        text-align: left;
    }
</style>
<div id="leaderboard">
    <h2>Leaderboard - Top 5</h2>
    <table id="leaderboard-entries">
        <thead>
            <tr>
                <th>Rank</th>
                <th>Name</th>
                <th>Points</th>
            </tr>
        </thead>
        <tbody>
        </tbody>
    </table>
</div>

<script>
    console.log("Hi")
    const csvUrl = "https://docs.google.com/spreadsheets/d/e/2PACX-1vTA1WYeDBls3ood7HPl8IAX03ubHn4hHKOv8mP-y2Bj-H1Dbuvbl1WAIvSBR8CqkEd8J7yhFnKEWrVS/pub?output=csv";

    fetch(csvUrl)
        .then(response => response.text())
        .then(data => {
            // Split data by lines and commas
            const rows = data.trim().split("\n").slice(1); // Remove the header row
            const topFive = rows.slice(0, 5); // Get only the first 5 entries
            
            const leaderboardTable = document.getElementById("leaderboard-entries").getElementsByTagName("tbody")[0];
            leaderboardTable.innerHTML = ""; // Clear previous content
            
            topFive.forEach(row => {
                const [rank, name, points] = row.split(","); // Adjust indices as per CSV column order
                const tableRow = document.createElement("tr");
                
                const rankCell = document.createElement("td");
                rankCell.textContent = rank;
                tableRow.appendChild(rankCell);
                
                const nameCell = document.createElement("td");
                nameCell.textContent = name;
                tableRow.appendChild(nameCell);
                
                const pointsCell = document.createElement("td");
                pointsCell.textContent = points;
                tableRow.appendChild(pointsCell);
                
                leaderboardTable.appendChild(tableRow);
            });
        })
        .catch(error => console.error("Error loading leaderboard:", error));
</script>

 
*Last updated: <span id="last-updated">Loading...</span>*

<script>
    fetch(csvUrl)
        .then(response => response.text())
        .then(data => {
            const lastUpdated = new Date().toLocaleString();
            document.getElementById("last-updated").textContent = lastUpdated;
        })
        .catch(error => console.error("Error loading last updated time:", error));
</script>

To update the leaderboard, please contact the admin.