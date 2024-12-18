# Цель проекта

Создать электронный журнал, который объединяет функции учета посещаемости, успеваемости и взаимодействия преподавателей со студентами. Проект направлен на автоматизацию процессов, минимизацию ручной работы и обеспечение прозрачности данных для всех участников образовательного процесса.

---

# Ключевые проблемы текущих решений

1. **Устаревший интерфейс.**  
    Большинство существующих решений выглядит как "таблицы в Excel", не учитывая современные принципы UX/UI.
2. **Ограниченная функциональность.**  
    Текущие системы фиксируют данные, но не помогают с анализом, прогнозированием или автоматизацией.
3. **Отсутствие интеграции.**  
    Нет возможности объединить данные посещаемости, оценок и заданий в одном пространстве.
4. **Сложность использования.**  
    Преподаватели тратят время на рутинные задачи, например, ввод даты или подсчет пропусков вручную.

---

# Концепция улучшенного электронного журнала

**1. Модульный подход:**  
Система должна быть построена из модулей, которые можно адаптировать под конкретные нужды кафедры. Основные модули:

- **Посещаемость:** отметка присутствия/отсутствия.
- **Оценки:** выставление и анализ.
- **Статистика:** аналитика по студентам и группам.
- **Задания:** контроль сроков сдачи и уведомления.


**2. Автоматизация:**

- Автоматическое добавление текущей даты и времени.
- Вычисление статистики (например, подсчет пропущенных занятий, средний балл).
- Уведомления студентов о дедлайнах.
- Предиктивный анализ (например, прогноз оценки по посещаемости).


**3. Визуализация данных:**

- Графики, диаграммы и цветовая подсветка для удобного анализа успеваемости.
- "Тепловые карты" для анализа пропусков.

**4. Доступность:**

- Кроссплатформенность: веб-версия, мобильное приложение.
- Учет специфики образовательного процесса, например, различных типов занятий (лекции, лабораторные).

**5. Интеграция с ИИ:**

- Распознавание лиц для автоматической отметки посещаемости.
- Обработка рукописных документов, например, листов посещаемости.
- Анализ данных и рекомендации, например, выявление проблемных студентов.

---

# Уникальные возможности (USP)

- **Для преподавателей:**
    
    - Быстрое внесение данных (например, один клик для отметки посещаемости всей группы).
    - Детальная аналитика по предмету, группе или студенту.
    - Уведомления о сроках сдачи работ.
- **Для студентов:**
    
    - Прозрачный доступ к своим данным: пропускам, оценкам, заданиям.
    - Уведомления о новых заданиях и дедлайнах.
    - Статистика собственной успеваемости в графическом виде.

---

# Функциональность системы

#### **1. Учет посещаемости**

- Быстрое добавление отметок (например, списком или через QR-коды).
- Возможность указывать причины отсутствия (уважительная, неуважительная).
- История посещаемости для каждого студента.
- Автоматическое создание отчетов по посещаемости.

#### **2. Учет успеваемости**

- Выставление оценок за занятия, контрольные работы и задания.
- Система автоматической оценки (например, за выполнение теста в LMS).
- Средние баллы и анализ динамики успеваемости.

#### **3. Работа с заданиями**

- Отображение выполненных/невыполненных работ.
- Уведомления студентам о приближении дедлайна.

#### **4. Статистика и аналитика**

- Графики успеваемости.
- Подробный анализ пропусков по причинам.
- Выявление студентов "в зоне риска".

#### **5. Интеграция и расширения**

- Интеграция с системами Moodle, Blackboard или другой LMS.
- Синхронизация с календарями преподавателей и студентов


# Как можно реализовать учет посещаемости

### **1. Распознавание лиц с помощью камер (под вопросом)**

**Описание:**  
В аудитории устанавливается камера, которая фиксирует лица студентов. Система сравнивает изображения с базой данных (например, фотографиями из личных дел) и автоматически отмечает присутствие.

- **Преимущества:**
    - Минимум действий от преподавателя.
    - Возможность точного учета времени прихода/ухода.
- **Техническая реализация:**
    - Использовать OpenCV или TensorFlow для распознавания лиц.
    - Хранение биометрических данных с учетом законодательства.

**Необычные аспекты:**

- Система может учитывать студентов, выходящих и возвращающихся на занятие (например, для перерывов).
- Отображение онлайн-статистики на экране в аудитории: кто пришел, кто опоздал.

---

### **2. Использование QR-кодов**

**Описание:**  
Каждому студенту присваивается уникальный QR-код, который они сканируют на входе в аудиторию (например, через установленный сканер или приложение преподавателя).

- **Преимущества:**
    - Простота реализации.
    - Доступность для студентов, у которых есть смартфоны.
- **Техническая реализация:**
    - Преподаватель генерирует уникальный QR-код для занятия (например, с временным интервалом).
    - Система отмечает студентов, чьи QR-коды были просканированы.

**Необычные аспекты:**

- QR-код можно выводить на экран проектора, чтобы студенты сканировали его на входе.
- Какое-то приложение: Студенты получают уведомления с QR-кодом для входа на лекцию.

---

### **3. NFC-метки или карты доступа**

**Описание:**  
Каждому студенту выдается NFC-метка (например, карта или брелок), которую они прикладывают к считывателю на входе в аудиторию.

- **Преимущества:**
    - Быстрота и надежность.
    - Учет точного времени прибытия.
- **Техническая реализация:**
    - Установка NFC-считывателей на дверях аудиторий.
    - Хранение данных в системе университета.

**Необычные аспекты:**

- Использование смартфонов с поддержкой NFC вместо карт.
- Метка может использоваться для других нужд (доступ в общежитие, библиотеку).

---

### **4. Геолокация смартфонов**

**Описание:**  
Система проверяет местоположение студентов через их смартфоны и автоматически отмечает присутствие, если они находятся в аудитории.

- **Преимущества:**
    - Полностью автоматизированный процесс.
    - Удобство для студентов.
- **Техническая реализация:**
    - Мобильное приложение с разрешением на использование геолокации.
    - Привязка координат аудитории к системе.

**Необычные аспекты:**

- Функция определения опозданий по времени входа в аудиторию.
- Уведомления студентам, если они находятся не на паре (например, забыли про лекцию).

---

### **5. Умная перекличка через голосовые технологии (под вопросом)**

**Описание:**  
Преподаватель включает систему голосового опроса, где студенты подтверждают присутствие, говоря свою фамилию или фразу.

- **Преимущества:**
    - Не нужно никуда ходить или что-то сканировать.
    - Голосовая технология интегрируется с уже существующей базой студентов.
- **Техническая реализация:**
    - Использование Google Speech-to-Text API или аналогов для распознавания голоса.
    - Идентификация по ключевым словам (например, фамилии).

**Необычные аспекты:**

- Система может фиксировать, кто как отвечает (энергично или нет) и использовать это для анализа вовлеченности.

---

### **6. Bluetooth-маяки (Beacons)**

**Описание:**  
В аудитории устанавливаются Bluetooth-маяки, которые фиксируют смартфоны студентов с активированным Bluetooth.

- **Преимущества:**
    - Полностью бесконтактная система.
    - Возможность фиксировать точное время нахождения в аудитории.
- **Техническая реализация:**
    - Использование маяков BLE (Bluetooth Low Energy).
    - Мобильное приложение, которое соединяется с маяком и отправляет данные в систему.

**Необычные аспекты:**

- Маяк может автоматически приветствовать студентов и сообщать об изменениях расписания.
- Отслеживание плотности потока студентов (например, кто вышел из аудитории).

---

### **7. Распознавание по фотографиям группы (под вопросом)**

**Описание:**  
Преподаватель фотографирует аудиторию через специальное приложение, а система распознает всех присутствующих студентов.

- **Преимущества:**
    - Минимум технических требований (только камера).
    - Возможность проверки больших групп.
- **Техническая реализация:**
    - Анализ изображений с помощью нейронных сетей (например, Amazon Rekognition или OpenCV).

**Необычные аспекты:**

- Система может фиксировать расположение студентов (например, кто где сидит).

---

### **8. Биометрические датчики (под вопросом)**

**Описание:**  
Использование отпечатков пальцев или сканеров радужной оболочки глаз на входе в аудиторию.

- **Преимущества:**
    - Высокая точность и надежность.
    - Исключение возможности "отметить друга".
- **Техническая реализация:**
    - Установка биометрических терминалов на входе.
    - Синхронизация с базой данных студентов.

**Необычные аспекты:**

- Датчики могут использоваться не только для отметки посещаемости, но и для регистрации экзаменов.

---

### **9. Учет присутствия по активности Wi-Fi**

**Описание:**  
Система фиксирует присутствие студентов по их подключению к университетской Wi-Fi-сети.

- **Преимущества:**
    - Простота реализации.
    - Не требует от студентов дополнительных действий.
- **Техническая реализация:**
    - Идентификация по MAC-адресам устройств студентов.
    - Сравнение с расписанием занятий.

**Необычные аспекты:**

- Можно дополнительно использовать Wi-Fi-аналитику для мониторинга поведения студентов (например, где они чаще всего находятся).

---

### **10. Распознавание жестов (под вопросом)**

**Описание:**  
Система с использованием камеры фиксирует, как студенты поднимают руки или делают определенные жесты для отметки присутствия.

- **Преимущества:**
    - Интерактивный и необычный способ взаимодействия.
    - Подходит для лекций с активной аудиторией.
- **Техническая реализация:**
    - Использование алгоритмов машинного зрения.
    - Привязка жестов к списку студентов.

**Необычные аспекты:**

- Возможность использовать необычные жесты (например, машут рукой, чтобы "попрощаться" при выходе).

# Анализ аналогов: преимущества и недостатки

Для анализа я выделю три основных типа аналогов электронных журналов посещаемости:

1. **Школьные электронные журналы**
2. **Корпоративные системы учета времени**
3. **Простые таблицы Excel или Google Sheets**

---

### **1. Школьные электронные журналы (например, "Дневник.ру", "Сетевой город", "Электронная школа")**

**Преимущества:**

- **Привычный интерфейс.** Школьные журналы часто оформлены в виде таблиц, что интуитивно понятно для пользователей.
- **Функции оценки и посещаемости.** Можно отмечать оценки и присутствие учеников в одном месте.
- **Уведомления родителям и ученикам.** Автоматическая рассылка информации.
- **Поддержка отчетности.** Возможность выгрузки данных в удобном формате для анализа.
- **Возможность задания сроков.** Учителя могут назначать дедлайны для домашних заданий.

**Недостатки:**

- **Устаревший дизайн.** Многие системы выглядят неудобно и перегружены.
- **Ограниченные возможности автоматизации.** Например, отсутствуют функции интеграции с ИИ.
- **Нет ориентации на высшее образование.** Системы разработаны для школьных процессов и не учитывают особенности вузовских занятий (лекции, практики, лабораторные).
- **Много ручной работы.** Часто требуется вручную выбирать классы, предметы и заполнять информацию.

---

### **2. Корпоративные системы учета времени (например, "Bitrix24", "Trello", "Asana")**

**Преимущества:**

- **Широкая функциональность.** Возможность учета времени, постановки задач и мониторинга их выполнения.
- **Отчетность и статистика.** Создание графиков и аналитики по проектам или задачам.
- **Интеграции.** Поддержка интеграции с другими системами и календарями.
- **Мобильные версии.** Удобство работы через смартфон.

**Недостатки:**

- **Сложность настройки.** Требуется много времени для адаптации под образовательный процесс.
- **Нет учета посещаемости.** Основной упор на задачи, а не на физическое присутствие.
- **Отсутствие визуализации данных по студентам.** Корпоративные системы не поддерживают табличное или графическое отображение данных по группам студентов.
- **Высокая стоимость.** Для образовательных учреждений использование корпоративных решений может быть слишком дорогим.

---

### **3. Простые таблицы (Excel, Google Sheets)**

**Преимущества:**

- **Простота использования.** Не требует сложного обучения, понятен каждому пользователю.
- **Гибкость.** Можно настроить под конкретные нужды (например, создать свои формулы и таблицы).
- **Доступность.** Бесплатные или почти бесплатные решения.
- **Отсутствие зависимостей от сложного ПО.** Нет необходимости в серверной инфраструктуре.

**Недостатки:**

- **Отсутствие автоматизации.** Все данные нужно вводить вручную, что занимает время.
- **Невозможность анализа.** Нет встроенных аналитических инструментов для прогноза или визуализации.
- **Нет возможности интеграции.** Нельзя синхронизировать с другими системами (например, LMS или календарями).
- **Ограничения в использовании.** При увеличении объема данных таблицы начинают "тормозить".

| Критерий                  | Школьные журналы      | Корпоративные системы | Excel/Google Sheets   |
|---------------------------|-----------------------|------------------------|-----------------------|
| Учет посещаемости         | ✅                    | ❌                     | ✅                    |
| Учет оценок и заданий     | ✅                    | ✅                     | ✅                    |
| Автоматизация             | ❌                    | ✅                     | ❌                    |
| Статистика и анализ       | ✅                    | ✅                     | ❌                    |
| Простота использования    | ✅                    | ❌                     | ✅                    |
| Интеграция с другими системами | ❌                | ✅                     | ❌                    |
| Поддержка мобильных устройств | ✅                | ✅                     | ❌                    |
| Стоимость                 | Средняя              | Высокая               | Низкая                |

### **Общий вывод**

Аналоги, существующие на рынке, имеют определенные преимущества, но их функциональность ограничена либо из-за устаревших решений, либо из-за специфической ориентации на другие задачи (школы или компании).

**Почему текущие аналоги не подходят для нашего проекта?**

1. **Школьные журналы** ориентированы на базовый функционал без учета специфики вузов.
2. **Корпоративные системы** не подходят для работы с группами студентов и контроля посещаемости.
3. **Excel/Google Sheets** не обеспечивают автоматизацию и масштабируемость для больших групп.

### **Ценности, которые можно позаимствовать для нашего проекта:**

1. **Привычный интерфейс.** Табличный стиль с улучшенной визуализацией данных.
2. **Автоматическая отчетность.** Упрощение подготовки отчетов для преподавателей и кафедры.
3. **Интеграции.** Возможность подключения к внешним сервисам (LMS, календари).
4. **Гибкость в настройке.** Поддержка различных типов занятий, дедлайнов и причин пропуска.

**Недостатки, которых стоит избежать:**

1. Устаревший дизайн и сложность использования.
2. Отсутствие поддержки анализа и прогноза на основе данных.
3. Сложные настройки или необходимость ручной работы.


# Распределение обязанностей

### **Распределение 1: По уровням системы (Back-end + Front-end)**

Каждый разработчик берёт на себя свой уровень системы.

#### **Разработчик 1 (Back-end):**

- Создание базы данных:
    - Таблицы для хранения данных студентов, расписания, посещаемости, заданий.
- Реализация API:
    - Эндпоинты для работы с QR-кодами, статистикой, отметками о присутствии.
- Логика автоматизации:
    - Обработка данных (например, добавление отметок о посещаемости).
    - Генерация отчетов и статистики.
- Интеграция с внешними сервисами:
    - Возможная синхронизация с ИАИС университета.

#### **Разработчик 2 (Front-end):**

- Создание пользовательского интерфейса:
    - Для преподавателей: просмотр и редактирование посещаемости, статистика.
    - Для студентов: доступ к заданиям, успеваемости, отметкам.
- Разработка функционала для QR-кодов:
    - Интерфейс для генерации и сканирования.
- Поддержка мобильной версии:
    - Адаптация интерфейса для телефонов.
- Визуализация данных:
    - Графики, таблицы, списки, отображение статистики.

---

### **Распределение 2: По модулям системы (Посещаемость + Успеваемость)**

Каждый разработчик отвечает за отдельный функциональный модуль.

#### **Разработчик 1 (Модуль посещаемости):**

- Реализация автоматизации:
    - Генерация QR-кодов для отметки присутствия.
    - Учёт геолокации или взаимодействия с NFC/планшетами.
- Логика подсчёта статистики:
    - Количество пропусков, средняя посещаемость за период.
- Создание интерфейса для преподавателей:
    - Таблицы посещаемости, фильтры по датам.
- Экспорт данных:
    - Генерация отчетов (PDF, Excel).

#### **Разработчик 2 (Модуль успеваемости):**

- Управление заданиями:
    - Добавление, редактирование, установка сроков.
- Учёт оценок:
    - Фиксация выполненных работ и выставление баллов.
- Создание интерфейса для студентов:
    - Доступ к заданиям, успеваемости.
- Анализ данных:
    - Визуализация успеваемости (графики, подсветка оценок).

---

### **Распределение 3: По методологии Agile (Гибкое распределение)**

Оба разработчика работают совместно, разделяя задачи на короткие спринты, но с фокусом на определённых областях.

#### **Разработчик 1 (Технический фокус):**

- Проектирование системы:
    - Выбор архитектуры и технологий.
    - Настройка серверной инфраструктуры.
- Основная логика:
    - Работа с данными (добавление, обновление, удаление).
    - Реализация API для автоматизации.
- Интеграция с оборудованием:
    - Работа с NFC/QR-кодами.

#### **Разработчик 2 (Пользовательский фокус):**

- Интерфейсы:
    - Создание интуитивного UI/UX для преподавателей и студентов.
    - Адаптация системы для мобильных устройств.
- Визуализация данных:
    - Построение графиков и отчетов.
- Тестирование:
    - Проверка функциональности с точки зрения конечного пользователя.

---

### **Распределение 4: По приоритетам задачи**

Каждый разработчик отвечает за задачи, связанные с ключевыми целями проекта.

#### **Разработчик 1 (Автоматизация и основная логика):**

- Упрощение работы преподавателей:
    - Реализация функционала автоматической отметки присутствия.
    - Добавление подсказок и уведомлений для преподавателей.
- Автоматический расчёт статистики:
    - Успеваемость, пропуски, выполненные задания.
- Генерация отчетов.

#### **Разработчик 2 (Интерфейс и взаимодействие):**

- Разработка визуально удобных таблиц.
- Функции для студентов:
    - Просмотр заданий, оценок и посещаемости.
- Интеграция со сторонними сервисами:
    - Импорт/экспорт данных (например, для преподавателей).

### **Распределение 5: По преподавательскому и студенческому интерфейсу**

#### **Разработчик 1 (Преподавательский интерфейс и административная часть):**

- **Создание интерфейса для преподавателя:**
    - Разработка таблиц для учёта посещаемости: отображение данных по студентам, фильтрация по датам, возможность редактирования.
    - Реализация интерфейса для добавления и редактирования заданий: создание форм для ввода задач, установка сроков.
    - Подсистема для выставления оценок: отображение средней оценки, фильтрация студентов по результатам.
    - Механизм для генерации отчетов: создание PDF или Excel отчетов с данными по посещаемости, успеваемости, срокам выполнения заданий.
- **Статистика для преподавателя:**
    - Графики и диаграммы успеваемости и посещаемости (например, средний балл за неделю, пропуски).
    - Подсветка студентов с низкой успеваемостью или частыми пропусками.
    - Уведомления для преподавателя (например, когда задание сдано).

#### **Разработчик 2 (Студенческий интерфейс и взаимодействие):**

- **Создание интерфейса для студента:**
    - Разработка страницы с заданиями: доступ к заданиям, возможность сдачи работ, просмотр сроков выполнения.
    - Студенческая панель для отслеживания успеваемости и посещаемости: отображение статистики по посещаемости, общая информация по сдаче заданий.
    - Личный кабинет студента: информация о баллах, оценках, пропусках и выполненных заданиях.
- **Подсистема уведомлений для студентов:**
    - Напоминания о сроках сдачи заданий и приближающихся занятиях.
    - Уведомления о новых оценках или изменениях в расписании.
- **Интеграция с системами для студентов:**
    - Возможность просмотра расписания (связь с расписанием занятий через ИАИС или другую систему).
    - Просмотр статистики по выполненным заданиям и посещаемости через удобный интерфейс.