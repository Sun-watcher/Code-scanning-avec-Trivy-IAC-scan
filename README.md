# Analyse de code Infrastructure-as-Code avec Trivy

Ce dépôt contient un exemple d'analyse de code **Infrastructure-as-Code (IaC)** utilisant **Trivy** pour détecter des vulnérabilités et des mauvaises configurations dans des fichiers Terraform.

---

## 📦 Contenu du projet

- `main.tf` : Exemple de configuration Terraform créant un bucket S3 AWS.
- `.github/workflows/trivy-iac-scan.yml` : Workflow GitHub Actions exécutant Trivy pour analyser les fichiers IaC à chaque push ou pull request.
- `README.md` : Ce fichier.

---

## ⚡ Fonctionnement

1. Lorsqu'une modification est poussée sur la branche principale ou qu'une pull request est ouverte, le workflow GitHub Actions se déclenche automatiquement.
2. Trivy scanne les fichiers Terraform pour détecter :
   - Les vulnérabilités de sécurité
   - Les mauvaises configurations (ex: bucket S3 non chiffré)
3. Le job GitHub Actions échoue si des problèmes de gravité **HIGH** ou **CRITICAL** sont détectés.
4. Un rapport est généré et peut être consulté dans les artefacts du workflow.

---
