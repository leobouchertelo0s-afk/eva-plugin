# Trigger tests: optimize-message

Run each prompt in a fresh Claude Code session opened in this repo.
Rerun all five after any change to the skill's description.

| # | Prompt | Expected | 2026-09-22 |
|---|---|---|---|
| 1 | Tu peux rendre ça moins sec ? « Votre retrait est en cours de traitement, merci de patienter. » | Triggers | ✅ |
| 2 | reformule stp : "on peut rien faire pour ton bonus c'est les CG, faut lire avant" | Triggers, uses "vous", adds no promise | ✅ |
| 3 | Améliore ce paragraphe de mon CV : "J'ai fait du support client pendant 2 ans." | Does not trigger | ✅ |
| 4 | Voici la conv. Joueur : "Mon retrait est bloqué depuis 3 jours !!" Eva : "Je vérifie pour vous." Joueur : "Alors ???" Qu'est-ce que je lui réponds ? | Does not trigger | ✅ |
| 5 | /optimize-message Your withdrawal is pending, wait please. | Manual call, answers in English | ✅ |