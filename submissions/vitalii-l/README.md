# Likedex — підсумковий проєкт з Agentic Engineering

## Автор

Vitalii Levinton (GitHub: [vitali1024](https://github.com/vitali1024)).

## Проєкт

Likedex — розширення для Chrome, що створює локальне read-only дзеркало списку відео YouTube, які користувач позначив як уподобані, для швидкого перегляду, пошуку, фільтрування, сортування та перегляду докладних відомостей. Сторінка Options і бічна панель (Side Panel) працюють із локальним дзеркалом без запитів до YouTube під час звичайної взаємодії з бібліотекою.

## Код

[Публічний репозиторій Likedex](https://github.com/vitali1024/likedex) · [Подана версія проєкту](https://github.com/vitali1024/likedex/tree/3ec9f5143df135ae194e98db9c5810274aec042a)

## Демонстрація

Демонстраційне відео: очікується — посилання буде додано до PR подання.

## Докази застосування практик Agentic Engineering

| Практика | Докази | Що вони підтверджують |
|---|---|---|
| Контекст-інженерія | [AGENTS.md у коміті](https://github.com/vitali1024/likedex/blob/aa46ad8c8487d02a33965999943cec3212b489be/AGENTS.md); [схвалена людиною зміна правила допуску](https://github.com/vitali1024/likedex/commit/a70f972b6ca784cf4f457f58131188b19c2336a6); [реалізація runtime](https://github.com/vitali1024/likedex/commit/826f546a86c67fa633df1bb9e2694eaf54709537) | Правила належності бібліотеки власнику та fail-closed pruning вплинули на реалізацію; production Sync залишався заблокованим до отримання доказів перевірки в реальному середовищі та явного схвалення людиною. |
| Специфікації перед кодом (SDD) | [Початковий коміт зі специфікаціями](https://github.com/vitali1024/likedex/commit/aa46ad8c8487d02a33965999943cec3212b489be), перед [створенням каркаса проєкту](https://github.com/vitali1024/likedex/commit/6ca6bc2861b4e23cf7d975b842c24633895a3bbe); [уточнення меж фази 3](https://github.com/vitali1024/likedex/commit/754fc5028fb6b251d600e07a0e5b3b66ca523c70) | Специфікації було зафіксовано до написання коду; підготовку зупинили через суперечність у межах фаз і відновили після схваленого людиною уточнення. |
| Верифікація | [RED регресійний тест pruning](https://github.com/vitali1024/likedex/commit/b02dd363897aa7ef08fbd0140026372ac885af8a); [GREEN реалізація](https://github.com/vitali1024/likedex/commit/85745b4b217083ccbf970edc050586b77649ea04); [підсумкова команда та її вивід](https://github.com/vitali1024/likedex/blob/3ec9f5143df135ae194e98db9c5810274aec042a/docs/agentic/capstone-verification.md#final-agent-run-verification) | Регресійний тест безпеки додано до реалізації; підсумковий запуск `npm run verify` успішно пройшов 541 модульний тест і 13 тестів Chromium, а також перевірки лінтера, типів і збірок. |
| Цикли (loop engineering) | [Фактичний обмежений цикл синхронізації](https://github.com/vitali1024/likedex/blob/85745b4b217083ccbf970edc050586b77649ea04/docs/agentic/loops/sync-loop.md) | Перша реалізація: 55 тестів не пройшли через операцію над схемою з додатковими перевірками; точкове виправлення; друга ітерація: усі 225 тестів пройшли, цикл завершено. |

[Повідомлені людиною результати smoke-test у реальному середовищі та межі реалізації](https://github.com/vitali1024/likedex/blob/3ec9f5143df135ae194e98db9c5810274aec042a/docs/agentic/capstone-verification.md#human-reported-live-results): 71 прийнята сторінка, 3,547 віддзеркалених записів про належність відео до списку вподобаних; приблизно 3,403 відео доступні в основному режимі перегляду. Персональні дані, отримані від постачальника API, не публікуються.

Закоміченого звіту незалежного рецензента не знайдено, тому практика maker ≠ checker не заявляється. Елементи керування Export/Clear та повноцінним Disconnect, незалежна перевірка перед випуском, приймальні перевірки остаточного пакета, подання до Chrome Web Store та публічна верифікація OAuth залишаються незавершеними.
