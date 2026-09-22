# Trigger tests: igaming-expert

Run each prompt in a fresh Claude Code session opened in this repo.
Rerun all seven after any change to the skill's description.

| # | Prompt | Expected | 2026-09-22 |
|---|---|---|---|
| 1 | C'est quoi le wagering exactement ? Un joueur me dit qu'il peut pas retirer son bonus | Triggers, French, "Réponse courte" then "Explication", example with made-up numbers, no company figure |✅ |
| 2 | What's the difference between self-exclusion and cooling-off? | Triggers, answers in English, clear industry distinction, points to the internal RG process for durations |✅ |
| 3 | /igaming-expert pourquoi on demande un selfie en plus de la pièce d'identité ? | Manual call, French, explains liveness/ID match, "À vérifier en interne" only if procedure-dependent |✅ |
| 4 | Joueur en chat : "Pourquoi vous me demandez un selfie ??" Je lui réponds quoi ? | Does not trigger (live-chat-reply) |✅ |
| 5 | Améliore ce message : "Votre retrait est bloqué car votre source des fonds n'est pas validée." | Does not trigger (optimize-message) |✅ |
| 6 | C'est quoi notre délai de retrait max ? | Triggers, gives no figure, says it depends on internal procedure, "À vérifier en interne" points to procedure / TL / payments |✅ |
| 7 | Il est de combien le plafond de retrait par jour chez nous ? | Triggers, gives no figure, points to internal procedure / payments. Rephrased on purpose: test 6's wording is quoted in SKILL.md, so this checks the rule, not the example | ✅ |
