# MikroTik — DHCP Client

**DHCP Client** — це функція MikroTik, яка дозволяє маршрутизатору автоматично отримувати IP-адресу та інші мережеві параметри від DHCP Server.

Простими словами, DHCP Client дозволяє MikroTik автоматично отримати налаштування мережі від іншого маршрутизатора або провайдера.

## Для чого потрібен DHCP Client?

DHCP Client використовується для:

- Автоматичного отримання IP-адреси.
- Отримання маски підмережі.
- Отримання Gateway (шлюзу за замовчуванням).
- Отримання DNS-серверів.
- Підключення MikroTik до мережі без ручного налаштування IP-адреси.

## Як працює DHCP Client?

Наприклад, MikroTik підключений до іншого маршрутизатора через порт `ether1`.

Інший маршрутизатор працює як DHCP Server.

Процес отримання IP-адреси:

1. MikroTik надсилає DHCP Discover.
2. DHCP Server пропонує IP-адресу (DHCP Offer).
3. MikroTik надсилає запит на отримання адреси (DHCP Request).
4. DHCP Server підтверджує видачу адреси (DHCP ACK).
5. MikroTik отримує IP-адресу та інші мережеві параметри.

## Де знайти DHCP Client у WinBox?

Перейти:

`IP → DHCP Client`

Тут можна:

- Створити DHCP Client.
- Переглянути отриману IP-адресу.
- Перевірити стан підключення.
- Вказати інтерфейс для отримання IP-адреси.
- Видалити або змінити DHCP Client.

## Як налаштувати DHCP Client?

1. Відкрити **WinBox**.
2. Підключитися до MikroTik.
3. Перейти в `IP → DHCP Client`.
4. Натиснути `+`.
5. У полі **Interface** вибрати `ether1`.
6. Переконатися, що **Use Peer DNS** увімкнено, якщо потрібно отримувати DNS від DHCP Server.
7. Натиснути **Apply → OK**.

## Основні параметри

| Параметр | Опис |
|---|---|
| Interface | Інтерфейс, через який MikroTik отримуватиме IP-адресу. |
| Use Peer DNS | Дозволяє використовувати DNS-сервери, отримані від DHCP Server. |
| Use Peer NTP | Дозволяє використовувати NTP-сервери, отримані від DHCP Server. |
| Add Default Route | Дозволяє додати маршрут за замовчуванням, отриманий від DHCP Server. |
| Status | Показує поточний стан DHCP Client. |

## Як налаштувати DHCP Client через Terminal?

Додати DHCP Client на `ether1`:

```bash
/ip dhcp-client add interface=ether1 disabled=no