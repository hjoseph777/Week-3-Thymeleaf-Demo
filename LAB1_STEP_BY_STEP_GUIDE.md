# Lab 1 - Thymeleaf Demo: Step-by-Step Resolution Guide

Below is the step-by-step workflow required to successfully complete Lab 1. You can follow these steps directly in your terminal, IDE, and text editor.

> **Legend:** <span style="color:green">🟢 **GREEN = Completed**</span> &nbsp;|&nbsp; <span style="color:red">🔴 **RED = Needs to be done**</span>

---

## <span style="color:green">✅ Step 1A: GitHub Setup — Fork, Clone & Pull (COMPLETED)</span>

The repository is already cloned locally and connected to `origin`. These sub-steps are done.

<span style="color:green">

1. **Fork the Repository** — ✅ Already forked.
2. **Clone Your Fork** — ✅ Already cloned locally.
   ```bash
   git clone https://github.com/YOUR-USERNAME/Thymeleaf-Demo.git
   cd Thymeleaf-Demo
   ```
3. **Add Upstream Remote** *(if a main original repo exists)*:
   ```bash
   git remote add upstream https://github.com/ORIGINAL-REPO.git
   ```
4. **Pull Latest Changes** — ✅ Already up to date on `main`.
   ```bash
   git pull upstream main
   ```

</span>

---

## <span style="color:green">✅ Step 1B: Create a Feature Branch (COMPLETED)</span>

<span style="color:green">

Branch `feature/lab01-HarryJoseph` has been created and checked out. ✅

5. **Create a Feature Branch** — ✅ Done.
   ```bash
   git checkout -b feature/lab01-HarryJoseph
   ```

</span>

---

## <span style="color:green">✅ Step 2: Create the `AboutController` (COMPLETED)</span>

<span style="color:green">

`AboutController.java` has been created at `src/main/java/com/example/Thymeleaf/Demo/controllers/`. ✅

1. Navigate to the controllers package — ✅ Done.
   `src/main/java/com/example/Thymeleaf/Demo/controllers/`
2. Create **`AboutController.java`** — ✅ Done.
3. The following code was added to handle the `GET /about` endpoint — ✅ Done.

```java
package com.example.Thymeleaf.Demo.controllers;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class AboutController {

    @GetMapping("/about")
    public String getAboutPage() {
        // This directs Spring to look for an "about.html" file in your templates folder
        return "about";
    }
}
```

</span>

---

## <span style="color:green">✅ Step 3: Create the `about.html` Template (COMPLETED)</span>

<span style="color:green">

`about.html` has been created at `src/main/resources/templates/`. ✅

1. Navigate to the `templates` directory — ✅ Done.
   `src/main/resources/templates/`
2. Create **`about.html`** — ✅ Done.
3. The file includes the required `<h1>Tekken Reborn</h1>` heading, 2–3 sentences of content, a key features list, and uses the shared project fragments (navbar, assets) — ✅ Done.

```html
<!DOCTYPE html>
<!-- Include Thymeleaf namespace to use "th:" tags -->
<html lang="en" xmlns:th="http://www.thymeleaf.org">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Tekken Reborn</title>
    <!-- Linking the project's styles.css file via Thymeleaf href syntax -->
    <link rel="stylesheet" th:href="@{/styles.css}">
</head>
<body>
    <div class="container">

        <!-- Requirement: Display <h1> tag with "Tekken Reborn" text -->
        <h1>Tekken Reborn</h1>

        <!-- Requirement: Include at least 2-3 sentences of meaningful content -->
        <p>An epic fighting game where legendary warriors clash in the ultimate tournament. Choose your champion, master their unique combos, and rise to the top of the leaderboards to prove your skill!</p>
        <p>Experience breathtaking graphics, a robust multiplayer matchmaking system, and an all-new storyline that dives deep into the intricate lore of each character.</p>

        <!-- Be creative! Adding additional elements... -->
        <h3>Key Features:</h3>
        <ul>
            <li>Brand new "Heat System" mechanics</li>
            <li>Over 30 unique, fully playable fighters at launch</li>
            <li>Stunning, interactive arena environments</li>
        </ul>

        <br>
        <!-- Navigation link back to home -->
        <a th:href="@{/}">Return to Home</a>
    </div>
</body>
</html>
```
*(Feel free to tweak the content — add images, lists, or any extra HTML elements!)*

</span>

---

## <span style="color:red">❌ Step 4: Run & Test Locally (NOT DONE)</span>

<span style="color:red">

The app has not been tested yet. After completing Steps 2 and 3, do the following:

1. Open your terminal at the project root (`Thymeleaf-Demo` folder).
2. Start the local server:
   ```bash
   mvn spring-boot:run
   ```
3. Wait for the Spring console to confirm the app has started.
4. Open your browser and navigate to:
   [http://localhost:8080/about](http://localhost:8080/about)
5. Confirm you see your Tekken Reborn page with no errors.

</span>

---

## <span style="color:red">❌ Step 5: Commit and Push (NOT DONE)</span>

<span style="color:red">

Once testing is confirmed, save and submit your changes via Git.

1. Stop the running app in your terminal (`CTRL + C`).
2. Stage all changes:
   ```bash
   git add .
   ```
3. Commit with the required message:
   ```bash
   git commit -m "Lab 1: Implement About Controller"
   ```
4. Push your feature branch to GitHub:
   ```bash
   git push origin feature/lab-yourname
   ```
   *(Use the exact branch name you created in Step 1B)*
5. Go to your forked repository on GitHub — click **"Compare & pull request"** to open a Pull Request to the original repository.

</span>

---

Congratulations — once all steps are green, your lab is complete! 🎉
