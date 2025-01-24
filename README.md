<h1>
  React <img src="./assets/react.svg" width="40" height="40" />
</h1>

<h2>Найпопулярніші запитання та відповіді на співбесіді з React</h2>

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

<details>
<summary>5. Що таке JSX?</summary>

#### React

- **JSX (JavaScript XML)** — це синтаксис, який дозволяє писати структури UI у вигляді XML-подібного коду всередині JavaScript. JSX є розширенням JavaScript і використовується в React для опису, як виглядає інтерфейс.

#### Основні особливості JSX:

1. **XML-подібний синтаксис:** Нагадує HTML, але використовується у JavaScript.

```jsx
const element = <h1>Hello, world!</h1>;
```

2. **Вбудований JavaScript:** Ви можете писати JavaScript-код у фігурних дужках `{}`.

```jsx
const name = "Alice";
const element = <h1>Hello, {name}!</h1>;
```

3. **Трансляція:** JSX компілюється в звичайний JavaScript, використовуючи такі бібліотеки, як Babel.

```jsx
const element = <h1>Hello</h1>;
// Перетворюється в:
const element = React.createElement("h1", null, "Hello");
```

4. Атрибути: Використовуються як у HTML, але замість `class` пишеться `className`, а замість `for` — `htmlFor`.

```jsx
const input = <input type="text" className="input-field" />;
```

5. JSX повертає дерево елементів: JSX-вираз може повертати лише один кореневий елемент. Використовуйте `<React.Fragment>` або порожній тег `<>` для групування.

```jsx
return (
  <>
    <h1>Title</h1>
    <p>Description</p>
  </>
);
```

#### Переваги:

- Зручне створення UI-компонентів.
- Зрозумілий і читабельний синтаксис.
- Тісна інтеграція з JavaScript-логікою.

JSX не обов'язковий у React, але широко використовується через зручність і гнучкість.

</details>

<details>
<summary>6. Різниця між станом (state) та пропсами (props)?</summary>

#### React

#### Різниця між станом (state) та пропсами (props)

| Критерій             | State                                                                 | Props                                                    |
| -------------------- | --------------------------------------------------------------------- | -------------------------------------------------------- |
| Призначення          | Зберігає внутрішній стан компонента.                                  | Передає дані від батьківського компонента до дочірнього. |
| Змінюваність         | Може змінюватися всередині компонента.                                | Незмінні (read-only).                                    |
| Доступність          | Доступний тільки в компоненті, де визначений.                         | Доступний у дочірньому компоненті через атрибути.        |
| Ініціалізація        | Встановлюється в компоненті за допомогою `useState` або конструктора. | Визначається батьківським компонентом.                   |
| Область використання | Для збереження динамічних даних, що можуть змінюватися.               | Для передачі фіксованих або динамічних даних.            |
| Хто керує?           | Компонент, у якому state визначений.                                  | Батьківський компонент.                                  |

</details>

<details>
<summary>7. Що таке React Хуки (Hooks)?</summary>

#### React

- **React Хуки (Hooks)** — це функції, які дозволяють вам використовувати стан та інші можливості React без написання класів.

#### Основні типи хуків:

1. **useState** — дозволяє додавати стан в функціональні компоненти.

```jsx
const [state, setState] = useState(initialState);
```

2. **useEffect** — дозволяє виконувати побічні ефекти (наприклад, запити до API або підписки) у функціональних компонентах.

```jsx
useEffect(() => {
  // код для ефекту
}, [dependencies]); // залежності
```

3. **useContext** — доступ до значень контексту без необхідності використовувати компонент Consumer.

```jsx
const value = useContext(MyContext);
```

4. **useRef** — дозволяє створювати посилання на DOM-елементи або зберігати значення між рендерами без змін стану.

```jsx
const myRef = useRef(initialValue);
```

5. **useReducer** — альтернатива useState, зручна для управління складнішими станами через редуктори, подібно до Redux.

```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

6. **useMemo** — оптимізує обчислення значень, щоб уникнути непотрібних повторних обчислень.

```jsx
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

7. **useCallback** — повертає мемоізовану версію функції, щоб вона не створювалась знову при кожному рендері.

```jsx
const memoizedCallback = useCallback(() => {
  // функція;
}, [dependencies]);
```

#### Основні переваги:

- **Функціональні компоненти:** Замість класових компонентів ви можете використовувати функціональні компоненти з хуками.

- **Покращена читабельність:** Логіка можна розділити на декілька хуків, що зменшує кількість коду та підвищує модульність.

- **Перерозподіл логіки:** Хуки дозволяють повторно використовувати логіку в різних компонентах без створення складних ієрархій.

</details>

<details>
<summary>8. Що таке контекст (Context)?</summary>

#### React

- **Контекст (Context)** в React — це механізм для передачі даних через дерево компонентів без необхідності передавати ці дані через пропси на кожному рівні.

#### Як працює контекст:

1. **React.createContext()** — використовується для створення контексту.

```jsx
const MyContext = React.createContext(defaultValue);
```

2. **Provider** — компонент, який надає значення контексту. Він обгортає частину дерева компонентів і передає значення вниз через value.

```jsx
<MyContext.Provider value={}>
  <YourComponent />
</MyContext.Provider>
```

3. **Consumer** — компонент, який споживає значення контексту. Зазвичай використовує функцію як дочірній елемент, що отримує значення контексту.

```jsx
<MyContext.Consumer>
{value => }
</MyContext.Consumer>
```

4. **useContext** — хук, який дозволяє доступити значення контексту без необхідності використовувати Consumer.

```jsx
const value = useContext(MyContext);
```

#### Коли використовувати:

- Коли є потреба передавати дані між компонентами на різних рівнях ієрархії (наприклад, тема, мова або користувач).

- Коли вам не хочеться передавати пропси через кілька рівнів компонентів, що може ускладнити код.

#### Приклад використання:

```jsx
// Створення контексту
const ThemeContext = React.createContext("light");

// Компонент, який надає значення контексту
function App() {
  return (
    <ThemeContext.Provider value="dark">
      <ThemedComponent />
    </ThemeContext.Provider>
  );
}

// Компонент, який споживає значення контексту
function ThemedComponent() {
  const theme = useContext(ThemeContext);
  return <div>The current theme is {theme}</div>;
}
```

#### Переваги:

- Зручність в передачі глобальних значень.

- Покращує масштабованість програми, зменшуючи кількість переданих пропсів.

</details>

<details>
<summary>9. Що таке портал (Portal)?</summary>

#### React

- **Портал (Portal)** у React — це спосіб рендерити дочірні елементи в DOM-вузол, який знаходиться за межами DOM-ієрархії батьківського компонента.

#### Як працює:

- React забезпечує портали через метод `ReactDOM.createPortal`, який приймає два аргументи:

1. **React-елемент**, що потрібно рендерити.

2. **Цільовий DOM-вузол**, у який слід вставити елемент.

#### Синтаксис:

```jsx
ReactDOM.createPortal(child, container);
```

- **child** — React-елемент, який потрібно рендерити.

- **container** — DOM-вузол, де елемент буде вставлено.

#### Приклад використання:

```jsx
import React from "react";
import ReactDOM from "react-dom";

function Modal({ children }) {
  return ReactDOM.createPortal(
    <div className="modal">{children}</div>,
    document.getElementById("modal-root") // Цільовий вузол
  );
}

function App() {
  return (
    <div>
      <h1>Основний контент</h1>
      <Modal>
        <p>Це контент модального вікна</p>
      </Modal>
    </div>
  );
}
```

#### Де використовують портали:

- Модальні вікна.

- Спливаючі підказки (tooltips).

- Контекстні меню.

#### Особливості:

1. **Ієрархія подій:**

- Хоча елемент рендериться поза ієрархією DOM, обробка подій відбувається відповідно до React-ієрархії компонентів. Наприклад, події onClick підніматимуться до батьківських компонентів React.

2. Гнучкість: Портали дозволяють вставляти елементи в місця, які не вписуються в поточну структуру DOM.

#### Переваги:

- Легке управління "плаваючими" елементами.
- Збереження контексту React навіть за межами основної DOM-ієрархії.

</details>

<details>
<summary>10. Методи життєвого циклу компонента у React?</summary>

#### React

- Методи життєвого циклу компонента в React використовуються для управління різними етапами життя компонентів: створення, оновлення та видалення.

#### Основні фази життєвого циклу:

1. **Монтування (Mounting):** Коли компонент додається в DOM.

- **_constructor():_** Ініціалізація стану та прив'язка методів.

- **_static getDerivedStateFromProps(props, state):_** Оновлення стану перед рендером (рідко використовується).

- **_render():_** Рендерить JSX у віртуальний DOM.

- **_componentDidMount():_** Викликається одразу після додавання компонента в DOM. Використовується для запитів API, ініціалізації бібліотек.

2. **Оновлення (Updating):** Коли змінюються пропси або стан.

- **_static getDerivedStateFromProps(props, state):_** Викликається перед кожним рендером.

- **_shouldComponentUpdate(nextProps, nextState):_** Контролює, чи потрібно повторно рендерити компонент. За замовчуванням повертає true.

- **_render():_** Виконується для оновлення віртуального DOM.

- **_getSnapshotBeforeUpdate(prevProps, prevState):_** Отримує знімок перед змінами (наприклад, положення скролу).

- **_componentDidUpdate(prevProps, prevState, snapshot):_** Викликається після оновлення. Використовується для повторних запитів або роботи з DOM.

3. **Розмонтування (Unmounting):** Коли компонент видаляється з DOM.

- **_componentWillUnmount():_** Використовується для очищення ресурсів (наприклад, таймерів, підписок).

4. **Обробка помилок (Error Handling):** Коли компонент викликає помилку.

- **_static getDerivedStateFromError(error):_** Дозволяє оновити стан після помилки.

- **_componentDidCatch(error, info):_** Логування помилок.

#### Таблиця методів:

| Фаза                | Метод                        | Опис                                    |
| ------------------- | ---------------------------- | --------------------------------------- |
| **Монтування**      | `constructor()`              | Ініціалізація стану та налаштування.    |
|                     | `getDerivedStateFromProps()` | Оновлення стану перед рендером.         |
|                     | `render()`                   | Рендеринг JSX у віртуальний DOM.        |
|                     | `componentDidMount()`        | Виконується після додавання в DOM.      |
| **Оновлення**       | `getDerivedStateFromProps()` | Оновлення стану перед рендером.         |
|                     | `shouldComponentUpdate()`    | Визначає, чи потрібен повторний рендер. |
|                     | `render()`                   | Оновлює віртуальний DOM.                |
|                     | `getSnapshotBeforeUpdate()`  | Отримує знімок стану перед оновленням.  |
|                     | `componentDidUpdate()`       | Виконується після оновлення.            |
| **Розмонтування**   | `componentWillUnmount()`     | Очищення ресурсів перед видаленням.     |
| **Обробка помилок** | `getDerivedStateFromError()` | Оновлює стан у разі помилки.            |
|                     | `componentDidCatch()`        | Логування помилок.                      |

#### Сучасний підхід:

У функціональних компонентах замість методів життєвого циклу використовують **хуки**:

- `useEffect` замінює `componentDidMount`, `componentDidUpdate`, `componentWillUnmount`.

- `useState` для управління станом.

</details>

<details>
<summary>11. Яка історія еволюції React?</summary>

#### React

- Ось коротка історія еволюції React:

1. **2011**

- React створений у Facebook для внутрішніх потреб. Його розробив інженер Джордан Волке, щоб вирішити проблему ефективного оновлення інтерфейсу.

2. **2013**

- Facebook випустив React як open-source бібліотеку. Спочатку спільнота зустріла її скептично через використання JSX, який здавався незвичним.

3. **2015**

- Випущено React 0.14: розділено React і ReactDOM, що зробило бібліотеку більш модульною.

- Facebook представив React Native, що дозволило створювати нативні мобільні додатки за допомогою React.

4. **2016**

- Випущено React 15. Основні оновлення торкнулися покращення продуктивності через новий рендеринг-движок.

5. **2017**

- Випущено React 16 (Fiber). Fiber став новою архітектурою, що забезпечила покращену продуктивність та підтримку асинхронного рендерингу.

- Додано підтримку порталів і помилкових кордонів (Error Boundaries).

6. **2018**

- Facebook представив React Hooks, які дозволили використовувати стан і методи життєвого циклу у функціональних компонентах. Це стало революцією у способі створення компонентів.

7. **2019**

- Випущено React 16.8 з офіційною підтримкою хуків.

- Покращено ефективність Concurrent Mode (експериментально).

8. **2020**

- Випущено React 17. Головна мета — спрощення поступового оновлення React у великих проектах.

- Додано підтримку сучасних інструментів і нових можливостей для роботи з JSX.

9. **2022 і далі**

- Випущено React 18. Головними нововведеннями стали Concurrent Rendering, новий API useTransition та useDeferredValue, які покращують продуктивність у динамічних додатках.

#### Основні зміни за час еволюції:

- Від класових компонентів до функціональних з хуками.

- Підтримка серверного рендерингу (SSR).

- Concurrent Mode для плавного оновлення інтерфейсу.

- Інтеграція React із мобільною розробкою через React Native.

React залишився популярним завдяки високій продуктивності, зручності використання та постійній підтримці від Facebook.

</details>

<details>
<summary>12. Які основні функції React?</summary>

#### React

#### Основні функції React:

1. **Декларативний підхід**

- React дозволяє створювати інтерактивний інтерфейс, описуючи, як він повинен виглядати, а бібліотека сама оптимізує оновлення DOM.

2. **Компонентна структура**

- Додаток будується з незалежних, багаторазових компонентів, які спрощують розробку, тестування та підтримку.

3. **Віртуальний DOM**

- React використовує Virtual DOM для ефективного оновлення реального DOM, що значно покращує продуктивність.

4. **Односпрямований потік даних**

- Дані передаються від батьківських компонентів до дочірніх через props, що спрощує управління станом.

5. **Хуки (Hooks)**

- Дозволяють використовувати стан і методи життєвого циклу у функціональних компонентах.

6. **JSX**

- Розширення JavaScript для опису UI в синтаксисі, схожому на HTML.

7. **React Native**

- Можливість створювати нативні мобільні додатки з використанням тих самих принципів, що і для вебу.

8. **Екосистема**

- Великий набір бібліотек та інструментів, таких як React Router, Redux, Context API.

9. **Підтримка серверного рендерингу (SSR)**

- Дозволяє оптимізувати SEO та прискорювати початкове завантаження сторінок.

10. **Управління станом**

- За допомогою useState, Context API, Redux чи інших бібліотек.

Ці функції роблять React потужною і гнучкою бібліотекою для створення сучасних додатків.

</details>

<details>
<summary>13. Яка різниця між елементом і компонентом?</summary>

#### React

#### Різниця між елементом і компонентом у React:

| Критерій                    | Елемент                                              | Компонент                                                                                          |
| --------------------------- | ---------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| **Визначення**              | Об'єкт, що описує, як має виглядати інтерфейс.       | Функція або клас, який повертає React-елементи.                                                    |
| **Тип**                     | Нероздільний (immutable).                            | Багаторазовий і може мати стан (state).                                                            |
| **Синтаксис створення**     | `React.createElement` або JSX (`<div />`).           | Функція або клас (`function MyComponent() {}` або `class MyComponent extends React.Component {}`). |
| **Призначення**             | Представляє окремий вузол у DOM.                     | Інкапсулює логіку та структуру інтерфейсу.                                                         |
| **Можливість використання** | Використовується для створення UI на базовому рівні. | Використовується для побудови складних структур із бізнес-логікою.                                 |
| **Приклад**                 | `<h1>Hello</h1>`                                     | `function Hello() { return <h1>Hello</h1>; }`                                                      |

- Елемент — це "будівельний блок", а компонент — "конструктор" для створення складних інтерфейсів.

</details>

<details>
<summary>14. Як створити компоненти в React?</summary>

#### React

#### У React компоненти можна створювати двома способами:

1. **Функціональний компонент**

- Це проста функція, яка повертає React-елементи.

```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

// Використання:
<Greeting name="John" />;
```

2. **Класовий компонент**

- Це клас, який успадковується від React.Component і обов’язково має метод render.

```jsx
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}

// Використання:
<Greeting name="John" />;
```

#### Відмінності:

- Функціональні компоненти простіші та краще підходять для компонентів без стану.

- Класові компоненти використовуються для складніших компонентів із власним станом або методами життєвого циклу.

**Примітка:** Сучасний підхід передбачає використання функціональних компонентів із хуками замість класових.

</details>

<details>
<summary>15. Коли використовувати компонент класу замість функціонального компонента?</summary>

#### React

- Класові компоненти використовувалися, коли потрібна була одна або кілька з цих функцій:

1. **Робота зі станом (state):** Раніше функціональні компоненти не підтримували локальний стан, тому використовували класи для цього.
   Сьогодні хуки (useState, useReducer) дозволяють функціональним компонентам працювати зі станом.

2. **Методи життєвого циклу:** Класи забезпечували доступ до методів, таких як componentDidMount, componentDidUpdate, componentWillUnmount, для управління компонентом на різних етапах його існування.
   Зараз це вирішується хуком useEffect.

3. **Обробка складної логіки:** Якщо логіка потребувала кількох методів і доступу до властивостей через this, класи виглядали логічним вибором.
   Сучасний підхід — хуки, які дозволяють інкапсулювати логіку.

#### Коли класи більше не потрібні:

- Починаючи з React 16.8, функціональні компоненти з хуками замінили потребу у класових компонентах. Тому в нових проєктах перевагу варто віддавати функціональним компонентам. Класи використовуються лише для підтримки застарілого коду.

</details>

<details>
<summary>16. Що таке чисті компоненти (Pure Components)?</summary>

#### React

- **Чисті компоненти (Pure Components)** — це спеціальні класові компоненти React, які автоматично оптимізують рендеринг. Вони реалізують поверхневе порівняння пропсів і стану, щоб запобігти зайвим оновленням, якщо значення пропсів або стану не змінилися.

#### Як створити чистий компонент?

- Чистий компонент створюється шляхом успадкування від React.PureComponent.

```jsx
import React, { PureComponent } from "react";

class MyComponent extends PureComponent {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}

// Використання:
<MyComponent name="John" />;
```

#### Як працює `PureComponent`?

- Виконує поверхневе порівняння (`shallow comparison`) пропсів і стану у методі `shouldComponentUpdate`.

- Якщо пропси та стан не змінилися, компонент не рендериться повторно.

#### Коли використовувати `PureComponent`?

- Коли пропси та стан є простими структурами (примітивні значення або неглибокі об'єкти).

- Для підвищення продуктивності в компонентах, які часто оновлюються.

#### Обмеження:

1. **Глибоке порівняння:** `PureComponent` не враховує зміни всередині вкладених об'єктів або масивів.

- Наприклад, якщо ви оновлюєте об'єкт, але посилання на нього залишається незмінним, компонент не оновиться.

```jsx
this.setState({ data: { ...this.state.data, key: "new value" } }); // Обхідна
```

2. **Не працює з функціональними компонентами.**

- Альтернатива: використовувати `React.memo` для оптимізації функціональних компонентів.

```jsx
const MyComponent = React.memo(function MyComponent(props) {
  return <h1>Hello, {props.name}!</h1>;
});
```

</details>

<details>
<summary>17. Що таке стан (state) у React?</summary>

#### React

- **Стан (state)** у React — це об'єкт, який використовується для зберігання даних, що можуть змінюватися з часом, і впливають на рендеринг компонента. Стан дозволяє компонентам React бути динамічними і реагувати на події, введення користувача тощо.

#### Особливості стану:

1. **Локальний для компонента:** Стан доступний тільки в тому компоненті, де він визначений.

2. **Змінюється асинхронно:** React об'єднує виклики setState для оптимізації рендерингу.

3. **Ініціалізується в конструкторі** (для класових компонентів) або через useState (у функціональних компонентах).

#### У класових компонентах:

```jsx
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  increment = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}
```

#### У функціональних компонентах (з хуком `useState`):

```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

#### Основні відмінності між станом і пропсами:

- **State** — локальний для компонента і може змінюватися.

- **Props** — передаються зовні і є незмінними (immutable).

</details>

<details>
<summary>18. Що таке пропси (props) в React?</summary>

#### React

- **Пропси (props)** в React — це об'єкт, який містить дані, що передаються від батьківського компонента до дочірнього. Вони використовуються для налаштування компонентів і є незмінними (immutable).

#### Особливості пропсів:

1. **Передаються зверху вниз** (унідіrectional data flow) — від батьківського компонента до дочірнього.

2. **Незмінні** — компонент не може змінювати отримані пропси.

3. **Динамічні** — значення пропсів можуть змінюватися, якщо змінюються дані в батьківському компоненті.

#### Використання пропсів:

1. **У функціональному компоненті:**

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}!</h1>;
}

// Використання:
<Welcome name="John" />;
```

2. **У класовому компоненті:**

```jsx
Копіювати;
Редагувати;
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}

// Використання:
<Welcome name="Jane" />;
```

#### Передача пропсів:

```jsx
function App() {
  return (
    <div>
      <Welcome name="Alice" />
      <Welcome name="Bob" />
    </div>
  );
}
```

- Результат:

```
Hello, Alice!
Hello, Bob!
```

#### Деструктуризація пропсів:

```jsx
function Welcome({ name }) {
  return <h1>Hello, {name}!</h1>;
}
```

#### Значення пропсів за замовчуванням:

```jsx
function Welcome({ name = "Guest" }) {
  return <h1>Hello, {name}!</h1>;
}

// Використання:
<Welcome />; // Виведе: Hello, Guest!
```

- Пропси забезпечують компонентам React гнучкість і можливість повторного використання.

</details>

<details>
<summary>19. Яка різниця між обробкою подій HTML і React?</summary>

#### React

#### Різниця між обробкою подій у HTML та React:

| Критерій                     | HTML                                                                    | React                                                                                 |
| ---------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **Прив’язка події**          | Вказується як атрибут: `<button onclick="handler()">`.                  | Використовується camelCase: `<button onClick={handler}>`.                             |
| **Тип функції**              | Посилання на глобальну функцію або рядок із JavaScript-кодом.           | Прив’язка до функції компонента (зазвичай вказується як метод або стрілочна функція). |
| **Додавання слухачів подій** | Обробники додаються вручну через `addEventListener`.                    | React автоматично керує прив’язкою через віртуальний DOM.                             |
| **Контекст `this`**          | Потрібно вручну встановлювати контекст, якщо використовується в класах. | React автоматично зберігає правильний контекст у функціональних компонентах.          |
| **Стандартна поведінка**     | Необхідно явно викликати `return false` для припинення поведінки.       | Використовується `event.preventDefault()` для зупинки стандартної поведінки.          |
| **Сумісність**               | Обробляє лише реальні DOM-події.                                        | Використовує "SyntheticEvent", що є обгорткою над нативними подіями.                  |
| **Кросбраузерність**         | Потрібно вручну враховувати відмінності між браузерами.                 | React забезпечує кросбраузерну сумісність через SyntheticEvent.                       |
| **Прив’язка контексту**      | Часто вимагає використання `bind`.                                      | У класових компонентах потрібен `bind`, у функціональних — ні.                        |

#### Приклад у HTML:

```html
<button onclick="alert('Clicked!')">Click me</button>
```

#### Приклад у React:

```jsx
function handleClick() {
  alert("Clicked!");
}

function App() {
  return <button onClick={handleClick}>Click me</button>;
}
```

#### SyntheticEvent у React:

- React використовує обгортку над нативними подіями, яка нормалізує поведінку між різними браузерами та підвищує продуктивність.

</details>

<details>
<summary>20. Які ключові переваги використання React?</summary>

#### React

#### Ключові переваги використання React

1. **Швидкість**: Завдяки Virtual DOM React мінімізує взаємодії з реальним DOM, що підвищує продуктивність.

2. **Компонентний підхід**: Код розбивається на багаторазово використовувані компоненти, що спрощує розробку та підтримку.

3. **Одностороння передача даних**: Потік даних у React відбувається в одному напрямку (зверху вниз), що полегшує дебагінг.

4. **Велика спільнота**: React має величезну екосистему бібліотек, інструментів і розширень.

5. **Сумісність із мобільною розробкою**: Використовуючи React Native, можна створювати кросплатформені мобільні додатки.

6. **JSX**: Синтаксис, який дозволяє писати JavaScript разом із HTML, що підвищує читабельність коду.

7. **Підтримка хуків**: Спрощення роботи зі станом та життєвим циклом у функціональних компонентах.

8. **SEO-дружність**: Серверний рендеринг за допомогою інструментів, таких як Next.js, покращує SEO-оптимізацію.

9. **Гнучкість**: React можна інтегрувати в будь-який проєкт або фреймворк без значних змін у коді.

10. **React DevTools**: Інструмент для налагодження, який дозволяє зручно аналізувати компоненти та стан додатка.

</details>

<details>
<summary>21. Що таке синтетичні події в React?</summary>

#### React

- **Синтетичні події (Synthetic Events)** у React — це обгортки для нативних DOM-подій, які надають однаковий інтерфейс для обробки подій на різних браузерах. React створює SyntheticEvent для кожної події, що дозволяє працювати з подіями в уніфікованому вигляді, забезпечуючи кросбраузерну сумісність і покращуючи продуктивність.

#### Основні характеристики:

1. **Кросбраузерність:** SyntheticEvent абстрагує особливості роботи з подіями в різних браузерах, забезпечуючи однакову поведінку.

2. **Оптимізація:** SyntheticEvent використовує пул об'єктів, що дозволяє зменшити витрати на створення нових об'єктів подій.

3. **Одноразове використання:** Після обробки події об'єкт SyntheticEvent "повертається" в пул, і його не можна використовувати після цього. Для асинхронних операцій потрібно зберігати подію в окремій змінній.

4. **Інтерфейс:** SyntheticEvent має такі ж методи, як і стандартні нативні події (наприклад, `preventDefault()`, `stopPropagation()`).

#### Приклад використання:

```jsx
function handleClick(event) {
  // SyntheticEvent має доступ до методу preventDefault()
  event.preventDefault();
  console.log("Button clicked!");
}

function App() {
  return <button onClick={handleClick}>Click me</button>;
}
```

- У цьому прикладі event — це SyntheticEvent, який працює аналогічно до нативної події, але з покращеними можливостями.

</details>

<details>
<summary>22. Як оновити стан компонента?</summary>

#### React

- У React стан компонента оновлюється за допомогою методу `setState` у класових компонентах або `useState` у функціональних компонентах.

#### Класові компоненти:

- Стан оновлюється через `this.setState()`.

- **_Приклад:_**

```jsx
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  increment = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}
```

#### Функціональні компоненти:

- Стан оновлюється через функцію, отриману з `useState`.

- **_Приклад:_**

```jsx
import React, { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
}
```

#### Примітки:

1. **Асинхронність:** `setState` і `useState` працюють асинхронно. Для оновлення стану на основі попереднього значення використовуйте функціональний підхід:

```jsx
this.setState((prevState) => ({ count: prevState.count + 1 }));
setCount((prevCount) => prevCount + 1);
```

2. **Не оновлюйте стан напряму:** Модифікація стану без використання `setState` або `useState` не викликає повторний рендеринг.

</details>

<details>
<summary>23. Що таке вбудовані умовні вирази?</summary>

#### React

- **Вбудовані умовні вирази** в JavaScript (зокрема у React) — це механізми, що дозволяють вбудовувати умови безпосередньо в JSX для умовного рендерингу елементів або компонентів. Це дозволяє зробити код компактнішим і зручнішим для розуміння.

#### Основні методи:

1. **Оператор умови (тернарний оператор):** Це один із найпоширеніших способів для умовного рендерингу елементів в JSX. Він має такий синтаксис:

```jsx
умова ? вираз_якщо_правда : вираз_якщо_неправда;
```

**Приклад:**

```jsx
const isLoggedIn = true;

function App() {
  return <div>{isLoggedIn ? <p>Welcome, User!</p> : <p>Please log in</p>}</div>;
}
```

2. **Логічний оператор AND (&&):** Цей метод дозволяє відображати компонент або елемент тільки тоді, коли умова є true. Якщо умова не виконується, нічого не буде рендеритись.

**Приклад:**

```jsx
const isUserAdmin = true;

function App() {
  return <div>{isUserAdmin && <p>You have admin privileges</p>}</div>;
}
```

- У цьому випадку `<p>You have admin privileges</p>` буде відображено лише, якщо `isUserAdmin` — це `true`.

3. **IF перед поверненням JSX:** Можна також використовувати звичайні умовні оператори if перед поверненням JSX, коли умова має бути більш складною або коли потрібно виконати декілька умовних дій.

**Приклад:**

```jsx
function App() {
  let content;
  if (isLoggedIn) {
    content = <p>Welcome back!</p>;
  } else {
    content = <p>Please sign in.</p>;
  }

  return <div>{content}</div>;
}
```

#### Переваги:

- Вбудовані умовні вирази дозволяють писати більш чистий і компактний код.

- Вони покращують читаємість і зменшують використання додаткових умовних конструкцій.

#### Важливо:

- В React не можна використовувати інструкції `if` безпосередньо в JSX. Однак можна застосувати їх перед поверненням JSX.

</details>

<details>
<summary>24. Як обробляти події в React?</summary>

#### React

- В React обробка подій працює схоже на стандартний JavaScript, але з деякими відмінностями. Події в React є синтетичними, що означає, що вони мають абстракцію поверх реальних подій браузера, що забезпечує крос-браузерну сумісність.

#### Основні принципи обробки подій в React:

1. **Синтетичні події:** Всі події в React обгорнуті в об'єкт **SyntheticEvent**, який є крос-браузерною реалізацією стандартних подій DOM. Це дозволяє обробляти події однаково в усіх браузерах.

2. **Використання camelCase для подій:** У React події записуються у форматі camelCase замість стандартного нижнього регістру (наприклад, `onClick` замість `onclick`).

3. **Передача функцій як обробників подій:** Події в React обробляються за допомогою функцій, які передаються через атрибути компонентів.

#### Приклад обробки події `click`:

```jsx
import React, { Component } from "react";

class MyButton extends Component {
  handleClick = () => {
    alert("Button clicked!");
  };

  render() {
    return <button onClick={this.handleClick}>Click Me</button>;
  }
}

export default MyButton;
```

#### Приклад з функціональним компонентом:

```jsx
import React, { useState } from "react";

function MyButton() {
  const [count, setCount] = useState(0);

  const handleClick = () => {
    setCount(count + 1);
  };

  return <button onClick={handleClick}>Clicked {count} times</button>;
}

export default MyButton;
```

#### Особливості обробки подій:

1. **Не потрібно використовувати `addEventListener`:** В React немає необхідності вручну додавати або видаляти обробники подій. Це автоматично керується бібліотекою React.

2. **Збереження контексту в методах класових компонентів:** Якщо методи класових компонентів використовуються як обробники подій, контекст (`this`) потрібно прив'язати або через стрілкові функції, або вручну в конструкторі.

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
    // Прив'язка методу
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState({ count: this.state.count + 1 });
  }

  render() {
    return (
      <button onClick={this.handleClick}>
        Clicked {this.state.count} times
      </button>
    );
  }
}
```

3. **Передача параметрів у функцію обробника:** Якщо потрібно передати додаткові аргументи в обробник події, можна використовувати стрілкові функції або функції з параметрами.

```jsx
function MyButton({ label }) {
  const handleClick = (event, label) => {
    console.log(label);
  };

  return (
    <button onClick={(event) => handleClick(event, label)}>{label}</button>
  );
}
```

#### Обробка подій в DOM:

- Всі події, що відбуваються в React, працюють за принципом делегування подій, де один обробник подій реєструється для всього дерева компонентів і пропускається через React SyntheticEvent.

</details>

<details>
<summary>25. ???</summary>

#### React

- Coming Soon... 😎
</details>
