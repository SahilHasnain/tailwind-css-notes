# Tailwind CSS Installation

Tailwind CSS ko install karne ke do popular tareeqe hain:

## 1. Tailwind ko CDN se Install Karna (Easy Tareeqa)

Agar tum sirf Tailwind seekhne ke liye practice kar rahe ho ya chhoti si website banana chahte ho to CDN ka use karo. Isme koi install karne ki zarurat nahi hoti, sirf ek link copy kar ke HTML file me daal do.

**Example:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tailwind CDN Example</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 flex justify-center items-center h-screen">
  <div class="bg-white p-6 rounded shadow-lg">
    <h1 class="text-2xl font-bold text-blue-600">Hello Tailwind!</h1>
    <p class="text-gray-600">Yeh Tailwind ka CDN version hai.</p>
  </div>
</body>
</html>
```

Matlab:
- `cdn.tailwindcss.com` se Tailwind load ho jaata hai
- Tum HTML me Tailwind ki classes ka use kar sakte ho directly

## 2. NPM + Tailwind CLI Installation (Professional Projects ke liye)

Jab tum ek badi project pe kaam kar rahe ho (jaise React, Next.js ya kisi company ke liye website), to tum Tailwind ko NPM se install karte ho jisse tum customization aur optimization kar sakte ho.

### Steps:

1. **Folder banao aur usme terminal open karo**
   ```bash
   mkdir my-tailwind-project
   cd my-tailwind-project
   ```

2. **NPM initialize karo:**
   ```bash
   npm init -y
   ```

3. **Tailwind install karo:**
   ```bash
   npm install -D tailwindcss
   npx tailwindcss init
   ```

4. **File structure banao:**
   ```
   /my-tailwind-project
   │
   ├── /src
   │   └── index.html
   ├── /styles
   │   └── input.css
   ├── tailwind.config.js
   └── package.json
   ```

5. **input.css me Tailwind ke directives likho:**
   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```

6. **Tailwind ko build karo:**
   ```bash
   npx tailwindcss -i ./styles/input.css -o ./dist/output.css --watch
   ```

7. **HTML file me CSS link karo:**
   ```html
   <link href="./dist/output.css" rel="stylesheet">
   ```

### Command Explanation

`npx tailwindcss -i ./styles/input.css -o ./dist/output.css --watch` ka meaning hai:

- `npx tailwindcss` - Tailwind ka CLI run karo bina install kiye globally
- `-i ./styles/input.css` - Input file ka path jahan tumne @tailwind directives likhe hain
- `-o ./dist/output.css` - Output file jahan Tailwind final CSS likhega
- `--watch` - File ko continuously dekhte raho, agar kuch change ho to output file update kar do

Jab tum ye command chalate ho, Tailwind:
- Tumhare input CSS ko padhta hai
- Saari Tailwind ki built-in classes generate karta hai
- Unko output.css me likh deta hai
- Aur agar tum classes ya custom config me kuch change karte ho, to automatically update bhi karta hai

### Summary:

| Method | Use Kab Karein? | Easy hai? | Customize Kar Sakte Ho? |
|--------|-----------------|-----------|-------------------------|
| CDN | Practice / Chhoti Site | Haan | Nahi |
| NPM | Real Projects | Thoda Setup | Haan (full control) | 