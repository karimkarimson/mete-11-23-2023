# Aufgabe 2023.11.23
### Aufgabe 1 
- Workflow: Ein Workflow in GitHub Actions ist eine automatisierte Abfolge von Jobs und Steps, die in Reaktion auf bestimmte Ereignisse in einem GitHub-Repository ausgeführt wird.
- Job: Ein Job ist eine Sammlung von Steps, die auf dem gleichen Runner parallel oder sequenziell ausgeführt werden.
- Step: Ein Step ist eine einzelne Aufgabe innerhalb eines Jobs. Schritte sind grundlegende Bausteine eines Jobs und führen spezifische Aktionen aus.
- Event: Ein Event ist eine Aktion oder Aktivität, die den Start eines Workflows auslöst, z. B. das Pushen von Code in ein Repository oder das Erstellen eines Pull Requests.
- Runner: Ein Runner ist eine virtuelle Maschine, auf der Jobs in einem Workflow ausgeführt werden. GitHub stellt standardmäßige Runner zur Verfügung, aber eigene Runner können auch konfiguriert werden.
- Actions: Actions sind wiederverwendbare automatisierte Abläufe, die in Workflows verwendet werden können. Sie können von GitHub bereitgestellte Aktionen oder benutzerdefinierte Aktionen aus dem Repository sein.


### Aufgabe 2

```yml
name: Parallel und Sequential Jobs

on:
  push:
    branches:
      - main

jobs:
  parallelJob:
    runs-on: ubuntu-latest
    steps:
      - name: Hello from Job 1
        run: echo "Hello from Job 1"

  sequentialJob:
    runs-on: ubuntu-latest
    needs: parallelJob
    steps:
      - name: Hello from Job 2
        run: echo "Hello from Job 2"

```