# Тестовое задание rating.kz

## ТЗ

Нужно реализовать реестр отчетов по объекту строительства, реестр фильтруется по объекту.
Далее нужно добавить кнопку Добавить и форму по добавлению отчета.
Форма по добавлению делиться на 3 шага, каждый шаг отображается на всю страницу, если ошибок нет то собираем все данные со всех шагов и единой моделькой отправляем в апи.
API по справочникам есть в контроллере Home, механизм по сохнранению не нужно делать, ваша задача сверстать с помощью бутстрапа реестр и форму, обратиться к существующим апи и проверить правильность заполнения, показать список ошибок при их наличии.

Фильтр по объекту
Реестр отчетов по строительному объекту(Наименование, Описание, Дата, Статус, Есть или нет замечания)
Форма по добавлению отчета по объекту

### Шаг 1

-Наименование*
-Описание
-Дата*
-Статус(В разработке, Принят)\*

### Шаг2

-Реестр замечаний (Категория, Дата, Описание)

### Шаг3

- Кнопка подтвердить и ошибки если таковые имеются
  \*-обязательные поля

## Backend API

### для реестра

get [178.90.223.230:6132/home/GetObj_JSON](178.90.223.230:6132/home/GetObj_JSON)

### справочник статусов

get [178.90.223.230:6132/home/GetStatus_JSON](178.90.223.230:6132/home/GetStatus_JSON)

### для получения информации с реестра по конкретной записи переход

get [178.90.223.230:6132/home/GetJournal_JSON?id={id}](178.90.223.230:6132/home/GetJournal_JSON?id={id})

### отправка запроса на сохранение, модель смотреть как GetJournal_JSON

post [178.90.223.230:6132/home/SetData](178.90.223.230:6132/home/SetData)

## Usage

`$ yarn install` - install dependencies

`$ yarn start` - start dev server

`$ yarn build` - get production build

---

## Implementation

- a site filter and a report table (name, description, date, status, whether there are remarks);
- a 3-step add form, each step full-page, with a progress indicator;
- step 2 holds a nested registry of remarks, step 3 is confirmation plus the list of validation errors;
- layout on Bootstrap 4 via `react-bootstrap`, validation with Formik + Yup.

Dictionaries and saving go through the API from the brief (`http://178.90.223.230:6132`). That is the company's own test environment — if it is unreachable, the lists stay empty.
