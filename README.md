# rx-template-massissuancerights
Шаблон разработки "Массовая выдача прав на папку и ее вложения".
Решение позволяет массово выдать права на папку, ее содержимое с обработкой всех подпапок. 
 
## Описание

1.	Модуль "Работа с правами"
2.	Асинхронный обработчик AsyncMassIssuanceRightsDocuments.
3.	Локализация новых элементов разработки.

## Варианты расширения функциональности на проектах
1.	Добавить запрет доступа.
2.	Добавить обработку задач, заданий, справочников.

## Архитектурно неочевидные моменты
Удобно использовать при миграции данных из других систем и быстрой выдачи нужных прав на документы любым субъектам прав. Нужно осторожно выдавать права.

## Порядок установки

Для работы требуется установленный Directum RX версии 3.6 или 4.1 - 4.10.

### Установка для ознакомления
1. Склонировать репозиторий rx-template-massissuancerights в папку.
2. Указать в _ConfigSettings.xml DDS:
``` xml
<block name="REPOSITORIES">
  <repository folderName="Base" solutionType="Base" url="" /> 
  <repository folderName="<Папка из п.1>" solutionType="Work" 
     url="https://github.com/DirectumCompany/rx-template-massissuancerights" />
</block>
```
### Установка для использования на проекте
Возможные варианты:

#### A. Fork репозитория.
1. Сделать fork репозитория rx-template-massissuancerights для своей учетной записи.
2. Склонировать созданный в п. 1 репозиторий в папку.
3. Указать в _ConfigSettings.xml DDS:
``` xml
<block name="REPOSITORIES">
  <repository folderName="Base" solutionType="Base" url="" /> 
  <repository folderName="<Папка из п.2>" solutionType="Work" 
     url="<Адрес репозитория gitHub учетной записи пользователя из п. 1>" />
</block>
```
#### B. Подключение на базовый слой.
Вариант не рекомендуется, так как при выходе версии шаблона разработки не гарантируется обратная совместимость.
1. Склонировать репозиторий rx-template-massissuancerights в папку.
2. Указать в _ConfigSettings.xml DDS:
```xml
<block name="REPOSITORIES">
  <repository folderName="Base" solutionType="Base" url="" /> 
  <repository folderName="<Папка из п.1>" solutionType="Base" 
     url="https://github.com/DirectumCompany/rx-template-massissuancerights" />
  <repository folderName="<Папка для рабочего слоя>" solutionType="Work" 
     url="<Адрес репозитория для рабочего слоя>" />
</block>
```
#### C. Копирование репозитория в систему контроля версий.
Рекомендуемый вариант для проектов внедрения.
1. В системе контроля версий с поддержкой git создать новый репозиторий.
2. Склонировать репозиторий rx-template-massissuancerights в папку с ключом `--mirror`.
3. Перейти в папку из п. 2.
4. Импортировать клонированный репозиторий в систему контроля версий командой:
`git push –mirror <Адрес репозитория из п. 1>`
