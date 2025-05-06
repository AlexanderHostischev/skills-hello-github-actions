# Лабораторна робота 8 завдання 1.1

## Курс "Hellp GitHub Actions" був успішно пройдений:

Файл welcome.yml https://github.com/AlexanderHostischev/skills-hello-github-actions/blob/main/.github/workflows/welcome.yml:
```yml
name: Post welcome comment
on:
  pull_request:
    types: [opened]
permissions:
  pull-requests: write
jobs:
  build:
    name: Post welcome comment
    runs-on: ubuntu-latest
    steps:
      - run: gh pr comment $PR_URL --body "Welcome to the repository!"
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          PR_URL: ${{ github.event.pull_request.html_url }}
```

Змінимо файл **README.md**, додамо емодзі у зміст:

<img width="1440" alt="Screenshot 2025-05-06 at 21 29 27" src="https://github.com/user-attachments/assets/93127cf0-beeb-4186-a61f-894897aaf49f" />
<img width="977" alt="Screenshot 2025-05-06 at 21 29 49" src="https://github.com/user-attachments/assets/6770bcb4-ed2f-4ec3-881b-2d8e790d0221" />

Після цих змін відкриємо Pull Request до вітки main і побачимо що воркфлоу спрацював та написав повідомлення у Pull Request:

<img width="962" alt="Screenshot 2025-05-06 at 21 29 59" src="https://github.com/user-attachments/assets/ac985229-93bb-4b7e-aa9a-030d964c2a00" />
<img width="930" alt="Screenshot 2025-05-06 at 21 30 19" src="https://github.com/user-attachments/assets/973650f7-c8d4-42da-add8-d5f57a1dfd6a" />

Як ми бачимо наш воркфлоу написав повідомлення у Pull Request.
