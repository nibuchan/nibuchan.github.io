## Generate file statis
~~~zsh
npx nuxi generate
~~~
hasilnya akan tersimpan di .output/public. Lalu jalankan perintah
~~~zsh
cd .output/public
~~~

## Commit Projek menggunakan git
1. Buat repositori di github dengan nama "username.github.io"
2. Inisialisasi Git (lakukan sekali saja)
    ~~~
    git init
    git remote add origin https://github.com/username/username.github.io
    git checkout -b main
    ~~~
3. Tambahkan file baru dan lakukan commit
    ~~~
    git add .
    git commit -m "Deploy"
    ~~~
4. Push ke repositori github
    ```
    git push -u origin main --force
    ```

## Commit projek menggunakan script package.json
Tambahkan script ini ke package.json
```
"scripts": {
  "generate": "nuxi generate",
  "deploy": "cd .output/public && git init && git add . && git commit -m 'Deploy' && git branch -M main && git remote add origin https://github.com/username/username.github.io.git && git push -f origin main"
}
```
setelah itu jalankan perintah
1. Generate file statis
    ```
    npm run generate
    ```
2. Deploy ke Github Pages
    ```
    npm run deploy
    ```
