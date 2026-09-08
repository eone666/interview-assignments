# Raison Test Task

Спасибо что откликнулись!

Чтобы выполнить тестовые задания сделайте форк этого репозитория или склонируйте и создайте новый репозиторий на github.
Сами задания описаны в readme.md в соответствующих папках.
Отправьте нам ссылку на репозиторий с готовыми заданиями.

Если в ходе диалога с нами вы уже выполняли задание по вёрстке то тест №1 вы можете пропустить.

---

## Running

Requires Node.js 18+. The two assignments are independent — install dependencies in each folder separately.

```bash
cd test-1-html+css
npm install
npm run dev
```

```bash
cd test-2-react
npm install
npm run dev      # client (vite) and express mock server (:4040) in one command
```

In the second assignment, requests to `/api/*` are proxied to the mock server — see [`test-2-react/vite.config.ts`](./test-2-react/vite.config.ts) and [`test-2-react/server.js`](./test-2-react/server.js).
