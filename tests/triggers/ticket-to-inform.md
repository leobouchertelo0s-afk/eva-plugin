# Trigger tests: ticket-to-inform

Run each prompt in a fresh Claude Code session opened in this repo.
Rerun all five after any change to the skill's description.

| # | Prompt | Expected | 2026-09-22 |
|---|---|---|---|
| 1 | Informe le joueur par mail. Ticket : "KYC: docs rejected, selfie blurry, ask new selfie with ID, 7 days max. Account limited meanwhile." | Triggers, French email, keeps "7 jours", no "account limited" wording unless rephrased | ✅ |
| 2 | Le service a répondu : "Bonus removed, T&C 4.2, multi-accounting suspected on 3 accounts." Fais le mail. | Triggers, no accusation, cites T&C 4.2, no mention of other accounts | ✅ |
| 3 | Reformule stp : "Votre retrait a été refusé, envoyez un relevé." | Does not trigger (optimize-message) | ✅ |
| 4 | Joueur en chat : "Pourquoi mon bonus a disparu ??" Qu'est-ce que je lui réponds ? | Does not trigger (live chat) | ✅ |
| 5 | /ticket-to-inform Payments: withdrawal approved, 48h to reach the bank. | Manual call, French email, keeps "48h" | ✅ |
