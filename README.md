# ИГРА КОСМИЧЕСКИЙ РЫЦАРЬ | GAME SPACE KNIGHT

Учебный проект, реализован в 2020 году на языке **`JavaScript`**. 

Браузерная игра, в которой персонаж, должен победить всех врагов. В игре персонаж имеет шкалу здоровья и школу энергии для борьбы с врагами.

###### Демонстрация
<dl>
  <dd>
    <dl>
      <dd>
        <h3><a href="https://riorustik.github.io/GameSSTU_1_1/">GitHub Pages</a> :octocat:</h3>
      </dd>
    </dl>
  </dd>
</dl> 

Проект написан с использованием технологии `Canvas`. 

Для взоимодействия с полотном сanvas необходимо найти элемент `<Canvas>` по "id" и взоимодействовать с ним через переменную, обьявив тип взоимодействия.

```
<canvas id="game"></canvas>

mapCanvas = document.getElementById("game");           
ctxMap = mapCanvas.getContext("2d");                
```
