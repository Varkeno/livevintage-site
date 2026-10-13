Lis CLAUDE.md. Ensuite, mets ce site en ligne sur https://www.livevintage.fr, en suivant les étapes dans l'ordre. Arrête-toi et demande-moi chaque fois qu'il faut une action de ma part (connexion à un compte, valeur à fournir).

1. Vérifications locales
   - Liste les fichiers et vérifie que tous les liens internes (href/src commençant par /) pointent vers un fichier existant. Avec cleanUrls, /guides/xxx correspond à guides/xxx.html.
   - Vérifie que chaque bloc JSON-LD est du JSON valide.
   - Vérifie qu'il ne reste aucun lien Payhip provisoire (PACK, TOME1…).
   - Crée un `.vercelignore` contenant `CLAUDE.md`, `PROMPT.md` et `.git`, pour que ces fichiers ne soient pas publiés.

2. Mentions légales
   - Demande-moi : nom et prénom, SIRET, adresse postale (ou de domiciliation), e-mail de contact.
   - Remplace les placeholders `[…]` dans mentions-legales.html. Il ne doit plus rester de crochet.

3. Git + GitHub
   - `git init`, premier commit.
   - Crée le repo public `Varkeno/livevintage-site` avec `gh repo create` et pousse sur main. Si `gh` n'est pas installé ou pas connecté, dis-moi exactement quoi faire (`gh auth login`), ou à défaut comment créer le repo à la main sur github.com.

4. Vercel
   - Utilise la CLI (`npx vercel`). Si je ne suis pas connecté, demande-moi de lancer `npx vercel login`.
   - Lie le projet, sans framework et sans build command, avec le dossier courant comme sortie. Déploie en production (`npx vercel --prod`).
   - Connecte le repo GitHub au projet Vercel pour que chaque push redéploie automatiquement. Si la CLI ne le permet pas, dis-moi où cliquer dans le dashboard.
   - Ajoute les domaines `www.livevintage.fr` (principal) et `livevintage.fr` (redirection 308 vers www).

5. DNS chez OVH (c'est moi qui le fais)
   - Récupère les enregistrements exacts demandés par Vercel (`npx vercel domains inspect livevintage.fr`, ou la sortie de l'ajout de domaine).
   - Donne-moi un tableau prêt à recopier dans OVH > Domaines > livevintage.fr > Zone DNS : type, sous-domaine, cible, et les enregistrements existants à supprimer (A et CNAME de @ et www, en gardant MX/SPF pour l'e-mail OVH).
   - Attends que je confirme. Vérifie ensuite avec `nslookup` que les DNS pointent vers Vercel, et avec `curl -I` que https://www.livevintage.fr répond 200 et que https://livevintage.fr redirige vers www.

6. Contrôle final en ligne
   - Teste `/`, `/guides`, un article, `/mentions-legales`, `/sitemap.xml`, `/robots.txt` et une URL inexistante (404).
   - Vérifie que CLAUDE.md n'est pas accessible publiquement.

7. Google Search Console (c'est moi qui le fais, guide-moi)
   - Explique-moi pas à pas comment ajouter la propriété de type « Domaine » livevintage.fr, avec l'enregistrement TXT à poser chez OVH.
   - Puis : soumettre https://www.livevintage.fr/sitemap.xml et demander l'indexation de la page d'accueil et des 6 guides avec l'outil Inspection d'URL.

8. Termine par un récap court : URL en ligne, repo, ce qui reste à faire de mon côté.
