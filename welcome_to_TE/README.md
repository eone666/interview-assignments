# Welcome to TileExpert

## Описание🧾

Тестовое задание на позицию front-end разработчика [TileExpert](https://jobs.tile.expert/) компании.

## TODO🖊

 * `fork` этот репозиторий
 * выполнить **все** задания (просто отредактируйте файлы с тестовыми задачами)
 * прикрепите ссылку на Ваш `forked` репозиторий в Вашу [анкету](https://jobs.tile.expert/ru/front-end-react-developer)

## Немного комфорта🏖

В каждом тестовом задании есть ссылка на песочницу, где Вы можете потестировать Ваш код на примере данной задачи.    
Результаты песочниц не учитываются, не рассматриваются и не мониторятся. Они созданны только для Вашего комфорта при выполнении заданий.    

## Ссылки🔖

 * [Сайт компании](https://jobs.tile.expert/ru)
 * [Наш продукт (сайт)](https://tile.expert/ru)

###### **P.S**: если у Вас есть вопросы по поводу тестового задания или Вы нашли некоторые ошибки, Вы можете создать *Issue* или *PullRequest* с подробным описанием вопроса или проблемы. Благодарим за Ваше внимание!

---

## Solutions

| Task | Problem | Solution |
| --- | --- | --- |
| [task_1](./task_1) | re-renders even when `props` do not change | `memo`, `PureComponent`, `shouldComponentUpdate` |
| [task_2](./task_2) | memoization broken by a new callback on every render | `useCallback` |
| [task_3](./task_3) | memoization broken by a default object in `props` | a constant outside the component + a custom comparator in `memo` |
| [task_4](./task_4) | a class component controlled through a `ref` has to become functional | `forwardRef` |
| [task_5](./task_5) | five components sharing the same logic and markup | one wrapper component, differences passed as `children` |
