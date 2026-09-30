# Lone Star Six Interactive Playbook

Static, mobile-first player playbook for the Texas 6s Stampede 7th and 8th grade team.

## Publish through GitHub and Cloudflare Pages

1. Create a GitHub repository and push this folder to the `main` branch.
2. In Cloudflare, open **Workers & Pages**, select **Create**, and choose **Pages**.
3. Connect the GitHub repository and select the `main` production branch.
4. Leave the framework preset as **None** and the build command blank.
5. Set the build output directory to `.` and deploy.
6. In the Pages project, open **Custom domains** and connect the team domain.

Every push to `main` will trigger a new Cloudflare deployment.

The site uses no external services, accounts, cookies, or analytics. Player progress is stored only in the browser with `localStorage`.

## Field Lab What If mode

Open the Field Lab, choose a situation, and press the large **Open What If Lab** button above the field. Players can drag any Lone Star or opponent marker to a new location. On release, the board explains the resulting spacing, matchup, substitution, field-rule, or defensive-shape consequence. Press reset to restore the designed play.

The goalie clear assumes a settled five-player zone. Wide outlets are the first reads. A middle outlet is used only when the receiver is already beyond midfield.

The substitution zone is marked on the right sideline at midfield. The Safe Change scenario routes both the exiting player and replacement through that sideline zone.

## Local preview

Run a static server from this folder, for example:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Files

- `index.html`: complete application, styles, diagrams, animations, quiz, and completion card.
- `sw.js`: optional offline cache after the first visit.
