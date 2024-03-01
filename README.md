## Задание

Сделать локальный шаблон CI и отдельный репозиторий с шаблонами, подключить их к своему основному репозиторию через include.

## Решение

Создал в том же репозитории файл `local-included-file.yml` с джобой:

```
local included file job:
  script:
    - echo "This is code from the file, which is included localy"
```

Инициализировал новый репозиторий, создал в нём файл `remote-included-file.yml` с джобой:

```
remote included file job:
  script:
    - echo "This is code from the file, which is included from another repository"
```

Результат:

```
include:
  - remote: https://gitlab.com/ci-cd7655047/5/-/raw/main/remote-included-file.yml
  - local: local-included-file.yml
```

Отработали обе джобы:

![](1.gif)

```
include:
  remote: 'https://oauth2:glpat-FwzyeNihxYYZjofyE_4E@gitlab.com/ci-cd7655047/5/-/raw/main/remote-included-file.yml'
```
