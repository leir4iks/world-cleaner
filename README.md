[![Download](https://img.shields.io/badge/Download-Latest-007BFF?style=for-the-badge&logo=github)](https://github.com/leir4iks/world-cleaner/releases/latest)

<div align="center">
  <br>
  <h1>WorldCleaner</h1>
  <br>
</div>

<div align="center">
  <strong>Плагин позволяет очищать мир, путем удаления чанков, в которых игроки провели мало времени.</strong>
</div>

- Плагин анализирует NBT тег каждого чанка - `InhabitedTime`. Этот тег отслеживает, как долго (в тиках) чанк находился в зоне видимости игрока. Если это время меньше значения, указанного в конфигурации, плагин удаляет чанк.

- Весь процесс выполняется в отдельном потоке, что не создает нагрузки на сервер (TPS).

### Команды

- Для использования команд требуется право `worldcleaner.command`.

- `/worldcleaner startclean <название_мира | all>` - Запустить очистку для указанного мира или всех миров.
- `/worldcleaner stopclean <название_мира | all>` - Остановить активный процесс очистки.
- `/worldcleaner listclean` - Показать статистику текущих процессов очистки.
- `/worldcleaner reload` - Перезагрузить конфигурацию.

### config.yml

```java
# /worldcleaner reload - перезагрузить конфиг, право worldcleaner.command

# порог времени, до которого чанки будут удаляться
# что это за время? это количество тиков, которые чанк был в зоне видимости игрока
# по умолчанию 60 секунд - 1200 тиков. если игрок чанк видел менее 60 секунд, то чанк удаляется
inhabited-time-threshold-ticks: 1200
```
