# Helm Package Management

## Agenda 

  1. Helm Installation
     * [Installation of kubectl under Linux](kubectl/installation/linux.md)
     * [Installation of helm under Linux](helm/installation/linux.md)
     * [Installation bash completion](helm/installation/bash-completion.md)

  1. Basics 
     * [Feature / No-Features von Helm](/helm/grundlagen/features-no-features.md)
     * [TopLevel Objekte](/helm/grundlagen/toplevel-objekte.md)

  1. Helm-Commands
     * [Setup repo](/helm/commands/repo.md)
     * [Download specific version of chart and unpack](/helm/commands/pull.md)
     * [Search in Repo und Artifacts Hub](/helm/commands/search.md)
     * [Show informations of charts online](/helm/commands/show.md)
     * [Upgrades and occuring problems](/helm/commands/upgrade.md)

 1. Helm Repository
     * [The most important helm commands](helm/commands/repo.md)

  1. Structure of a Helm - Charts
     * [Overview](helm/structure/overview.md)

  1. Basics of Helm-Charts
     * [Dev und Spaces (2 topics)](/helm/templates/spaces.md)

  1. Erstellen von Helm-Charts
     * [Erstellen eines Guestbooks](helm/create-charts/guestbook/01-guestbook.md)
     * [Hooks für Guestbook erstellen](/helm/create-charts/guestbook/02-guestbook-verbessern.md)
     * [Dependencies/Abhängigkeiten herunterladen](helm/create-charts/download-dependencies.md)
     * [Einfaches Testen](helm/test/simple-test.md)
     * [Input Validierung innerhalb von templates](helm/input-validation/example.md)
     * [Advanced Testing mit chart-testing](helm/test/advanced-testing/advanced-testing-with-chart-testing.md)
     * [Chart auf github veröffentlichen](helm/create-charts/publish/publish-on-github.md)

  1. FlowControl Helm-Charts (if,with,range)
     * [if](/helm/templates/flow-control/01-if.md)
     * [with](/helm/templates/flow-control/02-with.md)
     * [range](/helm/templates/flow-control/03-range.md)
      
  1. Security of helm-Chart
     * [Grundlagen / Best Practices](helm/security/best-practices.md)
     * [Security Encrypted Passwords in helm](/helm/security/secrets-password.md)

  1. Testing in Helm-Charts
     * [Testing in/von helm - charts](/helm/test/helm-test.md)
    
  1. Tipps & Tricks
     * [Set namespace in config of kubectl](/kubectl/set-namespace-in-config.md)
     * [Create Ingress Redirect](/helm/create-charts/example-ingress.md)
     * [Helm Charts - Development - Best practices](https://helm.sh/docs/howto/charts_tips_and_tricks/)

  1. Integration with other tools
     * [yamllint für Syntaxcheck von yaml - Dateien](helm/tools/yamllint.md)

  1. Troubleshooting und Debugging
     * [helm template --validate - gegen api-server testen](helm/test/helm-template-validate.md)
