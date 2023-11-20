<h3>
  <img src="../assets/React.png" width="16" height="16" />
  <span>React:</span>
</h3>

- [Что такое React?](https://youtu.be/7TvS0iKR3_c?t=638)
- Вопрос []()

  - Ответ[]()

- Вопрос []()

  - Ответ[]()

- Вопрос [Что такое `PureComponent`?]()

      - Ответ[`PureComponent` - это специальный компонент в React, который реализует метод `shouldComponentUpdate` с поверхностным (shallow) сравнением свойств (props) и состояния (state). В отличие от обычного компонента (`Component`), `PureComponent` автоматически выполняет эту проверку и решает, стоит ли компоненту обновляться.

  Основное отличие между `Component` и `PureComponent` заключается в том, что `PureComponent` автоматически выполняет проверку на изменения свойств и состояния, и если эти изменения не затрагивают компонент, он не будет перерисовываться. Это может повысить производительность в некоторых случаях, так как избегается избыточное обновление компонента.

  Пример использования `PureComponent`:

  ```jsx
  import React, { PureComponent } from 'react';

  class MyComponent extends PureComponent {
    render() {
      return <div>{this.props.value}</div>;
    }
  }
  ```

  В данном примере, если компонент `MyComponent` обновляется и ему передаются новые свойства (`value`), `PureComponent` автоматически проверит, изменились ли эти свойства по сравнению с предыдущими значениями, и решит, нужно ли обновление компонента.

  Важно отметить, что `PureComponent` использует поверхностное сравнение (shallow comparison) для объектов и массивов, поэтому если ваши свойства или состояние содержат вложенные структуры данных, изменения внутри этих структур могут быть пропущены, и компонент не будет обновлен. В таких случаях, вам может потребоваться использовать дополнительные методы для глубокого сравнения или использовать обычный `Component` с ручной реализацией `shouldComponentUpdate`, если это более удобно.]()

- Вопрос [Чем отличается useMemo от useCallback]()

  - Ответ[`useMemo` и `useCallback` в React используются для оптимизации производительности при работе с функциональными компонентами и мемоизации значений. Однако, они применяются в разных контекстах и решают разные задачи:

  1. **`useMemo`:**

  - **Цель:** `useMemo` используется для мемоизации результатов вычислений и предотвращения повторного вычисления значения при каждом рендере компонента.
  - **Когда использовать:** Используется, когда вам нужно вычислить и сохранить результат какого-то выражения (например, результат сложения или фильтрации массива) и предотвратить повторное вычисление при каждом рендере компонента.
  - **Пример:**
    ```jsx
    const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
    ```

  2. **`useCallback`:**

  - **Цель:** `useCallback` используется для мемоизации колбэк-функций и предотвращения их повторного создания при каждом рендере компонента.
  - **Когда использовать:** Используется, когда вам нужно передавать колбэк-функции в дочерние компоненты, и вы хотите предотвратить лишние рендеры дочерних компонентов при изменении родительского компонента.
  - **Пример:**
    ```jsx
    const handleClick = useCallback(
      () => {
        // Обработка клика
      },
      [
        /* зависимости */
      ]
    );
    ```

  **Общие черты:**

  - Оба хука принимают вторым аргументом массив зависимостей. Этот массив указывает, когда нужно повторно вычислить значение (в случае `useMemo`) или создать новую колбэк-функцию (в случае `useCallback`).
  - Оба помогают предотвратить ненужные вычисления или создания функций, что может улучшить производительность компонентов.

  **Различия:**

  - `useMemo` возвращает мемоизированное значение, тогда как `useCallback` возвращает мемоизированную колбэк-функцию.
  - `useMemo` используется для мемоизации значений, а `useCallback` - для мемоизации колбэк-функций.
  - `useMemo` полезен, когда вы хотите избежать повторных вычислений значений, тогда как `useCallback` - когда вы хотите избежать повторного создания функций.]()

- Вопрос []()

  - Ответ[]()

- Вопрос []()

  - Ответ[]()

- Вопрос []()

  - Ответ[]()

- Вопрос [Разница между теневым (Shadow) и виртуальным (Virtual) DOM?]()

  - Ответ[
    **Виртуальный DOM (Virtual DOM)**
    Виртуальный DOM — это концепция оптимизации процесса обновления реального DOM в веб-приложениях. Он представляет собой виртуальное представление текущего состояния DOM в виде дерева объектов. Вместо того чтобы напрямую взаимодействовать с реальным DOM при каждом изменении данных, библиотеки, такие как React, используют виртуальный DOM для вычисления минимальных изменений, которые необходимо внести в реальный DOM.

    Процесс работает примерно так:

    1. Изменения данных в вашем приложении приводят к созданию нового виртуального DOM.
    2. Новый виртуальный DOM сравнивается с предыдущим состоянием виртуального DOM.
    3. Вычисляются минимальные изменения (разница между новым и старым виртуальными DOM).
    4. Только эти минимальные изменения применяются к реальному DOM.

    Такой подход уменьшает количество манипуляций с реальным DOM, что ведет к улучшению производительности.

    **Теневой DOM (Shadow DOM):**

    Теневой DOM — это технология, предоставляющая изолированное DOM-дерево и стили для компонентов веб-приложения. Он позволяет создавать компоненты с их собственными стилями и структурами, которые изолированы от внешнего DOM. Это особенно полезно для создания переиспользуемых компонентов и веб-компонентов.

    Ключевые особенности теневого DOM:

    1. **Изоляция стилей:** Стили, определенные в теневом DOM, не затрагивают стили внешнего DOM, и наоборот.
    2. **Изолированная область видимости:** Элементы в теневом DOM видны только внутри этого теневого DOM, что предотвращает конфликты имен и стилей с внешним DOM.
    3. **Компоненты с теневым DOM:** Технология теневого DOM часто используется в создании веб-компонентов для обеспечения изоляции и управления стилями компонентов.

    **Вывод:**
    Оба концепта, виртуальный DOM и теневой DOM, направлены на улучшение производительности и структуризацию кода в веб-приложениях. Виртуальный DOM оптимизирует процесс обновления реального DOM, а теневой DOM обеспечивает изоляцию стилей и DOM для компонентов. Иногда эти термины могут использоваться в разных контекстах и технологиях.

    **Теневой DOM (Shadow DOM):**

    Теневой DOM представляет собой технологию, позволяющую создавать изолированные компоненты с их собственными стилями и структурами веб-приложения. Он обеспечивает изоляцию и скрытность вложенных компонентов от внешнего DOM (основного DOM-дерева).

    Основные концепции и функции теневого DOM:

    1. **Изоляция стилей:** Стили, определенные внутри теневого DOM, не влияют на стили внешнего DOM и наоборот. Это позволяет компонентам иметь свои уникальные стили, не создавая конфликтов с остальной частью приложения.

    2. **Изолированная область видимости:** Элементы внутри теневого DOM видны только внутри этого теневого DOM. Компоненты могут содержать свои собственные элементы, которые не пересекаются с элементами внешнего DOM, что способствует изоляции и уменьшению возможных конфликтов.

    3. **Сокрытие деталей реализации:** Теневой DOM предоставляет средства для сокрытия деталей реализации компонентов от внешнего кода. Это способствует созданию чистого API для использования компонентов.

    Пример использования теневого DOM:

    ```html
    <!DOCTYPE html>
    <html lang="en">
      <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <style>
          /* Стили внешнего DOM */
          div {
            color: red;
          }
        </style>
      </head>
      <body>
        <div id="app"></div>

        <script>
          const shadowRoot = document
            .getElementById('app')
            .attachShadow({ mode: 'open' });

          // HTML и стили внутри теневого DOM
          shadowRoot.innerHTML = `
          <style>
            div {
              color: blue;
            }
          </style>
          <div>Hello, Shadow DOM!</div>
        `;
        </script>
      </body>
    </html>
    ```

    В этом примере `<div>Hello, Shadow DOM!</div>` находится внутри теневого DOM, и его стили (синий цвет) изолированы от стилей внешнего DOM (красный цвет).

    **Разница Теневой DOM (Shadow DOM) / Виртуальный DOM (Virtual DOM)**

    1. **Область видимости:**

       - Теневой DOM предоставляет изолированную область видимости и стилей для компонентов. Это означает, что стили и DOM элементы внутри теневого DOM не влияют на стили и элементы в основном DOM и наоборот.

    2. **Изоляция стилей:**

       - Стили, определенные в теневом DOM, ограничены областью видимости этого теневого DOM. Это позволяет компонентам иметь свои уникальные стили без влияния на стили внешнего DOM.

    3. **Компоненты с теневым DOM:**

       - Теневой DOM часто используется в веб-компонентах для создания изолированных и переиспользуемых компонентов.

    **Виртуальный DOM (Virtual DOM):**

    1. **Концепция перерисовки:**

       - Виртуальный DOM представляет собой виртуальное представление текущего состояния реального DOM. Он используется для оптимизации процесса перерисовки и обновления DOM.

    2. **Эффективные обновления:**

       - Вместо непосредственного изменения реального DOM при каждом обновлении данных, React (и другие библиотеки) использует виртуальный DOM для вычисления минимального количества изменений и эффективного обновления реального DOM.

    3. **Реконсиляция:**

       - Процесс сравнения виртуального DOM с предыдущим состоянием и применения минимальных изменений для обновления реального DOM называется реконсиляцией.

    **Общее:**

    1. **Эффективность:**

       - Оба подхода направлены на улучшение производительности веб-приложений, хотя решают разные проблемы. Теневой DOM решает проблему изоляции компонентов, а виртуальный DOM — проблему эффективной перерисовки DOM.

    2. **Использование:**

       - Теневой DOM используется чаще в контексте веб-компонентов и Shadow DOM API, тогда как виртуальный DOM чаще ассоциируется с библиотеками, такими как React, для эффективного управления обновлениями DOM.

    В целом, теневой DOM и виртуальный DOM представляют различные концепции, и каждый из них решает свои специфические задачи в области разработки веб-приложений.

    ]()

- Вопрос [Что такое портал (`Portal`)?]()

  - Ответ[Портал (`Portal`) в React - это механизм, который позволяет рендерить дочерние элементы в DOM-узлы, которые находятся вне иерархии родительских компонентов. Это полезно, когда вам нужно отрендерить содержимое в другое место в DOM, не меняя свою иерархию компонентов.

  Чтобы использовать портал, вы можете использовать компонент `ReactDOM.createPortal(child, container)`. `child` - это React-элемент, который вы хотите отрендерить, а `container` - DOM-элемент, в который вы хотите его поместить.

  Пример:

  ```jsx
  import React, { useState } from 'react';
  import ReactDOM from 'react-dom';

  const Modal = ({ children, onClose }) => {
    const modalRoot = document.getElementById('modal-root');
    const el = document.createElement('div');

    React.useEffect(() => {
      modalRoot.appendChild(el);
      return () => modalRoot.removeChild(el);
    }, [el, modalRoot]);

    return ReactDOM.createPortal(
      <div className="modal">
        {children}
        <button onClick={onClose}>Close</button>
      </div>,
      el
    );
  };

  const App = () => {
    const [modalIsOpen, setModalIsOpen] = useState(false);

    return (
      <div>
        <button onClick={() => setModalIsOpen(true)}>Open Modal</button>
        {modalIsOpen && (
          <Modal onClose={() => setModalIsOpen(false)}>
            <p>Modal content goes here.</p>
          </Modal>
        )}
      </div>
    );
  };

  ReactDOM.render(<App />, document.getElementById('root'));
  ```

  В этом примере `Modal` - это компонент, который рендерит содержимое внутри портала. Портал создается с использованием `createPortal` и помещает содержимое в отдельный DOM-элемент, который добавляется к элементу с id `modal-root` внутри DOM. Это позволяет модальному окну отрендериться вне своего родительского компонента, сохраняя при этом структуру DOM-дерева вашего приложения.]()

- Вопрос []()

  - Ответ[]()

- Вопрос []()

  - Ответ[]()

- Вопрос []()

  - Ответ[]()

- [Перечислите особенности React?](https://youtu.be/7TvS0iKR3_c?t=671)
- [Что такое Virtual DOM? Как он работает с React?](https://youtu.be/7TvS0iKR3_c?t=740)
- [Для чего нужен атрибут `key` при рендере списков?](https://youtu.be/yvOXvZ8aEFo?t=526)
- [](https://youtu.be/yvOXvZ8aEFo?t=581)
- [Что такое Компонент высшего порядка (Higher-Order Component/HOC)?](https://youtu.be/yvOXvZ8aEFo?t=637)
- [Разница между управляемыми (controlled) и не управляемыми (uncontrolled) компонентами?](https://youtu.be/yvOXvZ8aEFo?t=684)
- [Методы жизненного цикла компонента в React?](https://youtu.be/RpcB5jnJvcI?t=35)
- [Стадии жизненного цикла компонента в React?](https://youtu.be/RpcB5jnJvcI?t=173)
- [Что такое React Reconciliation?](https://youtu.be/RpcB5jnJvcI?t=271)
- [Что такое контекст (`Context`)?](https://youtu.be/RpcB5jnJvcI?t=390)
- [Что такое React хуки (Hooks)?](https://youtu.be/RpcB5jnJvcI?t=475)
- [Что Такое `JSX`?](https://youtu.be/RpcB5jnJvcI?t=571)
- [Разница между состоянием(`state`) и пропсами(`props`)?](https://youtu.be/RpcB5jnJvcI?t=621)
- [Что такое React Fiber?](https://youtu.be/RpcB5jnJvcI?t=689)
- [Что такое фрагмент (`Fragment`)? Почему фрагмент лучше, чем `div`?](https://youtu.be/RpcB5jnJvcI?t=730)
- [Что такое синтетические события в React?](https://youtu.be/81yRgVQ1ciM?t=34)
- [Что такое React-ссылка (`ref`)? Как создать ссылку?](https://youtu.be/81yRgVQ1ciM?t=69)
- [Разница между теневым (Shadow) и виртуальным (Virtual) DOM?](https://youtu.be/81yRgVQ1ciM?t=112)
- [Назовите преимущества использования React?](https://youtu.be/81yRgVQ1ciM?t=170)
- [Что такое условный рендеринг (Conditional Rendering)? Как его выполнить?](https://youtu.be/81yRgVQ1ciM?t=224)
- [Что такое компонент-переключатель (Switching Component)?](https://youtu.be/81yRgVQ1ciM?t=265)
- [Разница между `React` и `ReactDOM`?](https://youtu.be/81yRgVQ1ciM?t=305)
- [Разница между компонентом и контейнером?](https://youtu.be/81yRgVQ1ciM?t=370)
- [Как React обрабатывает, или ограничивает использование пропсов определенного типа?](https://youtu.be/81yRgVQ1ciM?t=413)
- [Что такое строгий режим в React? Его преимущества?](https://youtu.be/81yRgVQ1ciM?t=469)
- [Что такое «бурение пропсов» (Prop Drilling)? Как его избежать?](https://youtu.be/81yRgVQ1ciM?t=532)
- [Что такое «опрос» (Polling)? Как его реализовать в React?](https://youtu.be/81yRgVQ1ciM?t=597)
- [Разница между элементом и компонентом?](https://youtu.be/81yRgVQ1ciM?t=663)
- [Что такое `ReactDOMServer`?](https://youtu.be/81yRgVQ1ciM?t=763)
- [Что такое предохранители (Error Boundaries)?](https://youtu.be/HBSAjY-xh3k?t=36)
- [Что такое «ленивая» (Lazy) функция?](https://youtu.be/HBSAjY-xh3k?t=103)
- [Разница между рендерингом и монтированием?](https://youtu.be/HBSAjY-xh3k?t=149)
- [Что такое `сhildren`?](https://youtu.be/HBSAjY-xh3k?t=191)
- [Что такое события указателя (Pointer Events)?](https://youtu.be/HBSAjY-xh3k?t=239)
- [Что такое инверсия наследования (Inheritance Inversion)?](https://youtu.be/HBSAjY-xh3k?t=301)
- [Как в React реализовать двустороннее связывание данных?](https://youtu.be/HBSAjY-xh3k?t=355)
- [Разница между классовым и функциональным компонентами?](https://youtu.be/xZLxdts7ZW4?t=664)
- [Разница между `useEffect()` и `componentDidMount()`?](https://youtu.be/xZLxdts7ZW4?t=754)
- [Преимущества хуков?](https://youtu.be/xZLxdts7ZW4?t=819)
- [Недостатки хуков?](https://youtu.be/__neFkxAO9s?t=793)
- [Правила (ограничения) использования хуков?](https://youtu.be/xZLxdts7ZW4?t=873)
- [Что такое поднятие состояния вверх (Lifting State Up)?](https://youtu.be/ngyOYuTrUk8?t=700)
- [Что делает метод `shouldComponentUpdate`?](https://youtu.be/ngyOYuTrUk8?t=748)
- [Разница между `createElement()` и `cloneElement()`?](https://youtu.be/ngyOYuTrUk8?t=816)
- [Что такое `useReducer()`?](https://youtu.be/GZUy2i6QN7o?t=257)
- [Как реализовать однократное выполнение операции при начальном рендеринге?](https://youtu.be/GZUy2i6QN7o?t=321)
- [Что такое распределенный компонент?](https://youtu.be/GZUy2i6QN7o?t=386)
- [Расскажите о хуках `useCallback()`, `useMemo()`, `useImperativeHandle()`, `useLayoutEffect()`?](https://youtu.be/GZUy2i6QN7o?t=449)
- [Как отрендерить HTML код в React-компоненте?](https://youtu.be/GZUy2i6QN7o?t=572)
- [Зачем в `setState()` нужно передавать функцию?](https://youtu.be/GZUy2i6QN7o?t=627)
- [Для чего предназначен метод `registerServiceWorker()` в React?](https://youtu.be/GZUy2i6QN7o?t=665)
- [Чем React Router отличается от обычной маршрутизации?](https://youtu.be/GZUy2i6QN7o?t=710)
- [Какие хуки были добавлены в React Router версии 5?](https://youtu.be/GZUy2i6QN7o?t=765)
- [Как передавать пропсы в React Router?](https://youtu.be/GZUy2i6QN7o?t=841)
- [Что такое Reselect и как он работает?](https://youtu.be/XtQPrt8G0n8?t=847)
- [Назовите основную цель React Fiber?](https://youtu.be/DgevxmyzymQ?t=30)
- [Какие типы данных может возвращать `render`?](https://youtu.be/DgevxmyzymQ?t=90)
- [Разница между `memo` и `useMemo`?](https://youtu.be/DgevxmyzymQ?t=166)
- [Что такое синтетические события (SyntheticEvent) в React?](https://youtu.be/DgevxmyzymQ?t=235)
- [Является ли React реактивным?](https://youtu.be/DgevxmyzymQ?t=291)
- [Техники оптимизации перфоманса React?](https://youtu.be/__neFkxAO9s?t=606)
- [Лучшие практики безопасности в React?](https://youtu.be/__neFkxAO9s?t=694)