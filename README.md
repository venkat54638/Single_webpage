![Screenshot (3)](https://github.com/user-attachments/assets/09a80043-3817-4b95-a3c6-d22e05975266)
![Screenshot (5)](https://github.com/user-attachments/assets/605c0b50-b5ec-4059-b559-b5838e84044d)
![Screenshot (4)](https://github.com/user-attachments/assets/22e7935f-a818-40ce-ad96-709a897b8dc8)
![Screenshot (6)](https://github.com/user-attachments/assets/2f626781-205e-4eae-9981-e855d722601b)
![Screenshot (7)](https://github.com/user-attachments/assets/037cb791-3b7d-4a2d-881a-201c3362a6d2)
This project demonstrates the GitHub Flow workflow by creating and managing branches, making commits, and resolving a merge conflict.
For Initialize Repository:
created folder with name single web page and in created a file Index.html
It was a web page.
then after I used these Command in initialize and commit then push the file.
  ```bash
  git init
  git add .
  git commit -m "initial commit"
  git branch M main
  git push origin main```

then after I created a seperate branch then make the changes and committed it by these commands.

  git branch feature/update-styling
  git switch feature/update-styling
  git commit -m "first commit"
  git push origin feature/update-styling
then after I created a seperate branch then make the changes and committed it by these commands.
 
  git branch feature/add-content
  git switch feature/add-content
  git commit -m "second commit"
  git push origin feature/update-styling 
then after I merged the both branches with main and committed it with these commands.
  
  git switch main
  git merge feature/update-styling
Here accept changes and complete Merge.
   git merge feature/add-content
Here accept changes and complete Merge.
  git push origin main
by these we can slove the merge conflict '''
Husky is tool leverages Git hooks to enforces code quality standards and run tests before commits and pushes,ensuring that only quality code is added to the repository.
commands:
" git init"
"npx husky-init && npm install"
"npm install --save-dev lint-staged"
here we need to change the package json file :
{
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged",
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  },
  "lint-staged": {
    "*.js": ["eslint --fix", "prettier --write"]
  }
}
for fixing the errors
"npx eslint . --fix"
"npx prettier --write "
"git commit -m "feat: added validation for user input"
here we will do continuous integrtions.
name: CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Install dependencies
        run: npm install

      - name: Run linting
        run: npm run lint

      - name: Run tests
        run: npm test
  
