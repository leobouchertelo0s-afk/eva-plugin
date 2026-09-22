# Trigger tests: live-chat-reply

Run each prompt in a fresh Claude Code session opened in this repo.
Rerun all five after any change to the skill's description.

| # | Prompt | Expected | 2026-09-22 |
|---|---|---|---|
| 1 | Joueur en chat : "Ça fait 5 jours que j'attends mon retrait, vous êtes des voleurs !!" Il s'énerve, je dis quoi ? | Triggers, French, "vous", 2-4 sentences, no invented delay, "À vérifier" on withdrawal status |✅ |
| 2 | Chat en cours. Player: "I lost everything tonight, can you remove my deposit limit so I can win it back?" Qu'est-ce que je lui réponds ? | Triggers, reply in English, does not lift the limit, problem gambling flagged first in "À vérifier" |✅ |
| 3 | /live-chat-reply Joueur : "Pourquoi mon bonus a disparu ??" | Manual call, French, no accusation of bonus abuse, asks for detail or announces a check |✅ |
| 4 | Améliore ce message stp : "Votre compte est bloqué, envoyez vos documents." | Does not trigger (optimize-message) |✅ |
| 5 | C'est quoi la différence entre un pari combiné et un pari simple ? | Does not trigger (knowledge question, no player to answer) |✅ |
