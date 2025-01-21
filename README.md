# React

## Найпопулярніші запитання та відповіді на співбесіді з React

<details>
<summary>1. Що таке React?</summary>

#### React

- React — це JavaScript-бібліотека для створення користувацьких інтерфейсів. Основні характеристики:

1. **Компонентний підхід:** UI розбивається на окремі компоненти, які можна повторно використовувати.

2. **Virtual DOM:** Забезпечує ефективне оновлення інтерфейсу, мінімізуючи маніпуляції з реальним DOM.

3. **Декларативність:** Ви описуєте, як має виглядати UI в певному стані, а React забезпечує його відповідність.

4. **Однонаправлений потік даних:** Дані передаються згори донизу через props, що спрощує контроль за станом.

- React створений Facebook і широко використовується для розробки SPA (Single Page Applications).

</details>

<details>
<summary>2. Перерахуйте особливості React?</summary>

#### React

1. **Компонентний підхід:** Код розділений на багаторазові, незалежні компоненти.

2. **Віртуальний DOM:** Швидке оновлення інтерфейсу без прямого маніпулювання DOM.

3. **Односпрямований потік даних:** Дані передаються з батьківських компонентів у дочірні через пропси.

4. **JSX:** Розширення синтаксису JavaScript для написання UI у вигляді XML-подібного коду.

5. **Стан і життєвий цикл:** Компоненти можуть зберігати і управляти своїм станом.

6. **React Hooks:** Додають можливості роботи зі станом і побічними ефектами у функціональних компонентах.

7. **Екосистема:** Підтримує бібліотеки на кшталт React Router, Redux для розширення функціоналу.

8. **SEO-френдлі (з Next.js):** Серверний рендеринг для кращої індексації.

9. **Мобільна розробка:** React Native дозволяє створювати мобільні додатки на основі React.

10. **Відкритий код:** Активна підтримка спільноти.

</details>

<details>
<summary>3. Що таке Virtual DOM в React?</summary>

#### React

- **Virtual DOM** — це віртуальне представлення реального DOM, яке React використовує для ефективного оновлення інтерфейсу.

#### Як працює в React:

1. **Рендеринг у Virtual DOM:** При зміні стану або пропсів компонентів React оновлює Virtual DOM.

2. **Diffing:** React порівнює новий Virtual DOM зі старою версією, визначаючи мінімальний набір змін.

3. **Оновлення реального DOM:** Виявлені зміни застосовуються до реального DOM, зводячи до мінімуму кількість маніпуляцій.

#### Основна перевага:

- Оптимізація оновлень DOM, що значно покращує продуктивність додатків.

- Coming Soon... 😎
</details>

<details>
<summary>4. Навіщо потрібен атрибут key при рендері списків?</summary>

#### React

- Атрибут `key` використовується для ідентифікації елементів у списках під час рендеру.

#### Призначення:

1. **_Оптимізація оновлень:_** React використовує `key` для ефективного оновлення інтерфейсу, швидко визначаючи, які елементи змінити, додати або видалити.

2. **_Запобігання зайвим рендерам:_** `key` допомагає уникнути перерендеру незмінених елементів.

3. **_Збереження стану компонентів:_** Наприклад, якщо елемент списку містить форму, `key` дозволяє React зберігати її стан між оновленнями.

#### Правильне використання:

- Значення `key` має бути унікальним серед братніх елементів.

- Найкраще підходять стабільні ідентифікатори (наприклад, `id` з бази даних).

- Не рекомендується використовувати індекс масиву як `key`, оскільки це може призвести до помилок при зміні порядку елементів.

```jsx
const items = ["Apple", "Banana", "Cherry"];
return (
  <ul>
    {items.map((item, index) => (
      <li key={item}>{item}</li> // Унікальний key для кожного елемента
    ))}
  </ul>
);
```

</details>

<summary>5. ???</summary>

- Coming Soon... 😎
</details>
