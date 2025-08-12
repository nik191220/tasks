# JavaScript Практичні Задачі: Closures, Prototype, Constructors

## Інструкції

- Виконуй задачі по порядку
- Пиши рішення у файлі `script.js`
- Позначай номер задачі коментарем (наприклад, `// Задача 1`)
- Тестуй свій код у браузері або Node.js

---

## ЧАСТИНА 1: CLOSURES (Замикання)

### Задача 1: Простий лічильник

Створи функцію `createCounter()`, яка повертає функцію-лічильник. Кожен виклик повернутої функції має збільшувати внутрішній лічильник на 1 і повертати його поточне значення.

**Приклад використання:**

```javascript
const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3
```

### Задача 2: Приватна змінна

Створи функцію `createSecretKeeper()`, яка приймає початкове значення секрету і повертає об'єкт з двома методами:

- `getSecret()` - повертає поточний секрет
- `setSecret(newSecret)` - встановлює новий секрет

**Приклад використання:**

```javascript
const keeper = createSecretKeeper("початковий секрет");
console.log(keeper.getSecret()); // "початковий секрет"
keeper.setSecret("новий секрет");
console.log(keeper.getSecret()); // "новий секрет"
```

### Задача 3: Лічильник з кроком

Створи функцію `createStepCounter(step)`, яка приймає параметр `step` і повертає функцію-лічильник, що збільшує значення на вказаний крок.

**Приклад використання:**

```javascript
const counter2 = createStepCounter(2);
console.log(counter2()); // 2
console.log(counter2()); // 4
console.log(counter2()); // 6

const counter5 = createStepCounter(5);
console.log(counter5()); // 5
console.log(counter5()); // 10
```

### Задача 4: Множення на число

Створи функцію `createMultiplier(multiplier)`, яка приймає число-множник і повертає функцію, що множить передане їй число на цей множник.

**Приклад використання:**

```javascript
const double = createMultiplier(2);
const triple = createMultiplier(3);

console.log(double(5)); // 10
console.log(triple(4)); // 12
```

### Задача 5: Акумулятор значень

Створи функцію `createAccumulator()`, яка повертає функцію, що накопичує всі передані їй числа і повертає їх суму.

**Приклад використання:**

```javascript
const accumulator = createAccumulator();
console.log(accumulator(5)); // 5
console.log(accumulator(3)); // 8
console.log(accumulator(2)); // 10
```

### Задача 6: Фабрика привітань

Створи функцію `createGreeter(greeting)`, яка приймає тип привітання і повертає функцію, що вітає людей з цим привітанням.

**Приклад використання:**

```javascript
const sayHello = createGreeter("Привіт");
const sayGoodMorning = createGreeter("Доброго ранку");

console.log(sayHello("Іван")); // "Привіт, Іван!"
console.log(sayGoodMorning("Марія")); // "Доброго ранку, Марія!"
```

### Задача 7: Лімітований лічильник

Створи функцію `createLimitedCounter(limit)`, яка створює лічильник з обмеженням. Коли лічильник досягає ліміту, він повертає повідомлення "Ліміт досягнуто!" замість збільшення.

**Приклад використання:**

```javascript
const limitedCounter = createLimitedCounter(3);
console.log(limitedCounter()); // 1
console.log(limitedCounter()); // 2
console.log(limitedCounter()); // 3
console.log(limitedCounter()); // "Ліміт досягнуто!"
```

---

## ЧАСТИНА 2: CONSTRUCTORS (Конструктори)

### Задача 8: Конструктор Студента

Створи конструктор `Student(name, age, course)`, який створює об'єкти студентів з властивостями `name`, `age`, `course` та методом `introduce()`, що повертає рядок з представленням студента.

**Приклад використання:**

```javascript
const student1 = new Student("Олена", 20, "Інформатика");
console.log(student1.introduce()); // "Привіт, я Олена, мені 20 років, навчаюся на курсі Інформатика"
```

### Задача 9: Конструктор Рахунку

Створи конструктор `BankAccount(owner, balance)`, який створює банківський рахунок з методами:

- `deposit(amount)` - поповнення рахунку
- `withdraw(amount)` - зняття коштів (не можна зняти більше, ніж є на рахунку)
- `getBalance()` - отримання поточного балансу

**Приклад використання:**

```javascript
const account = new BankAccount("Петро", 1000);
account.deposit(500);
console.log(account.getBalance()); // 1500
account.withdraw(200);
console.log(account.getBalance()); // 1300
```

### Задача 10: Конструктор Автомобіля

Створи конструктор `Car(brand, model, year)` з методами:

- `start()` - запуск двигуна (виводить повідомлення)
- `stop()` - зупинка двигуна
- `getInfo()` - повертає інформацію про автомобіль

**Приклад використання:**

```javascript
const car = new Car("Toyota", "Camry", 2020);
console.log(car.getInfo()); // "Toyota Camry 2020 року"
car.start(); // "Двигун запущено"
car.stop(); // "Двигун зупинено"
```

### Задача 11: Конструктор Книги

Створи конструктор `Book(title, author, pages)` з методами:

- `read(pagesRead)` - відмічає прочитані сторінки
- `getProgress()` - повертає відсоток прочитаного
- `isFinished()` - перевіряє, чи книга прочитана повністю

**Приклад використання:**

```javascript
const book = new Book("1984", "Джордж Орвелл", 300);
book.read(100);
console.log(book.getProgress()); // 33.33
console.log(book.isFinished()); // false
```

### Задача 12: Конструктор Калькулятора

Створи конструктор `Calculator()` з методами для базових математичних операцій:

- `add(a, b)`, `subtract(a, b)`, `multiply(a, b)`, `divide(a, b)`
- `getLastResult()` - повертає результат останньої операції

**Приклад використання:**

```javascript
const calc = new Calculator();
console.log(calc.add(5, 3)); // 8
console.log(calc.multiply(4, 2)); // 8
console.log(calc.getLastResult()); // 8
```

### Задача 13: Конструктор Завдання

Створи конструктор `Task(title, description)` з методами:

- `complete()` - позначає завдання як виконане
- `getStatus()` - повертає статус завдання
- `getDetails()` - повертає повну інформацію про завдання

**Приклад використання:**

```javascript
const task = new Task("Вивчити JS", "Прочитати про closures та prototypes");
console.log(task.getStatus()); // "В процесі"
task.complete();
console.log(task.getStatus()); // "Виконано"
```

---

## ЧАСТИНА 3: PROTOTYPE (Прототипи)

### Задача 14: Додавання методу до прототипу

Створи конструктор `Person(name, age)` і додай до його прототипу метод `sayHello()`, який виводить привітання з ім'ям людини.

**Приклад використання:**

```javascript
const person1 = new Person("Анна", 25);
const person2 = new Person("Максим", 30);
person1.sayHello(); // "Привіт, я Анна"
person2.sayHello(); // "Привіт, я Максим"
```

### Задача 15: Розширення прототипу Array

Додай до прототипу Array метод `getAverage()`, який повертає середнє арифметичне всіх чисел у масиві.

**Приклад використання:**

```javascript
const numbers = [1, 2, 3, 4, 5];
console.log(numbers.getAverage()); // 3
```

### Задача 16: Наслідування через прототип

Створи конструктор `Animal(name)` з методом `speak()` у прототипі, а потім створи конструктор `Dog(name, breed)`, який наслідує від Animal і має додатковий метод `wagTail()`.

**Приклад використання:**

```javascript
const dog = new Dog("Рекс", "Овчарка");
dog.speak(); // "Рекс издає звук"
dog.wagTail(); // "Рекс махає хвостом"
```

### Задача 17: Перевизначення методу прототипу

Створи конструктор `Vehicle(type)` з методом `move()` у прототипі. Потім створи конструктор `Airplane(model)`, який наслідує від Vehicle, але перевизначає метод `move()`.

**Приклад використання:**

```javascript
const vehicle = new Vehicle("автомобіль");
const airplane = new Airplane("Boeing 747");
vehicle.move(); // "автомобіль рухається по землі"
airplane.move(); // "Boeing 747 літає в небі"
```

### Задача 18: Ланцюг прототипів

Створи конструктор `Shape()` з методом `getInfo()`, конструктор `Rectangle(width, height)` який наслідує від Shape, і конструктор `Square(side)` який наслідує від Rectangle.

**Приклад використання:**

```javascript
const square = new Square(5);
console.log(square.getInfo()); // Має показати інформацію про квадрат
console.log(square.getArea()); // 25
```

### Задача 19: Додавання методу до існуючого прототипу

Додай до прототипу String метод `reverseWords()`, який повертає рядок з перевернутими словами (але не літерами в словах).

**Приклад використання:**

```javascript
const text = "Привіт світ JavaScript";
console.log(text.reverseWords()); // "JavaScript світ Привіт"
```

### Задача 20: Комбінування всіх концепцій

Створи конструктор `Counter(initialValue)` з методами в прототипі. Додай метод `createIncrementer()` який використовує closure для створення функції, що збільшує лічильник на фіксовану величину.

**Приклад використання:**

```javascript
const counter = new Counter(10);
const incrementBy3 = counter.createIncrementer(3);
console.log(incrementBy3()); // 13
console.log(incrementBy3()); // 16
console.log(counter.getValue()); // 16
```

---

## Примітки

- Кожна задача допоможе тобі зрозуміти різні аспекти closures, constructors та prototypes
- Не хвилюйся, якщо спочатку буде складно - це нормально!
- Експериментуй з кодом і тестуй різні варіанти
- Звертайся до мене за допомогою, коли будеш готовий для перевірки

Удачі в навчанні! 🚀
