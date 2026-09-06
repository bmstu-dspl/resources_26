# Python и uv

Курс использует обычный CPython 3.14 и uv. Зависимости устанавливаются только через uv.

1. Установите [Git](https://git-scm.com/downloads) и
   [uv по официальной инструкции](https://docs.astral.sh/uv/getting-started/installation/).
   Если uv уже установлен, при необходимости обновите его способом установки
   (для отдельного установщика — `uv self update`).
2. Клонируйте репозиторий и перейдите в него:

   ```sh
   git clone https://github.com/bmstu-dspl/resources_26.git
   cd resources_26
   ```

3. Установите окружение из lock-файла:

   ```sh
   uv sync --locked
   uv run --locked python --version
   ```

   uv сам загрузит Python 3.14 и создаст `.venv`. Нужен доступ к сети при первой
   установке. `.python-version` выбирает ветку 3.14; конкретный установленный
   patch-релиз виден в выводе команды. Активировать среду вручную не требуется.

4. Откройте тетради в браузере:

   ```sh
   uv run --locked jupyter notebook
   ```

   Либо откройте папку репозитория в VS Code, установите расширения Python и
   Jupyter, откройте `.ipynb` и выберите **Select Kernel → Python Environments →
   `.venv`**. На macOS/Linux интерпретатор — `.venv/bin/python`,
   на Windows — `.venv\Scripts\python.exe`.

5. Перед воспроизведением выполните **Restart Kernel → Run All**.
   Диалог выбора ядра должен указывать на окружение этого репозитория.

`uv sync --locked` не изменяет lock-файл. Обновления зависимостей делает
преподаватель отдельно; студентам не нужно запускать `uv lock --upgrade`.
Версионный диапазон проекта ограничен Python 3.14, чтобы переход на следующую
ветку не происходил незаметно.
