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

Коррдинат положения и начальные знаения задаются в конструкторе функции `Player()`     
```
this.srcX = 0;                      
    this.srcY = 0;                      
    this.drawX = 0;                   
    this.drawY = gameHeight-180;        
    this.width = 60;                   
    this.height = 75;                  
    this.speed = 7;                     
    this.isRight = true;        
    this.isLeft = false;               
    this.hp = 100;               
    this.mp = 100;                    
    this.isDie = false;
```

Функция смерти игрока
```
this.die = function(){                
    gameLoop = emptyLoop;
    this.isDie = true;
    document.getElementById("block").style.display = "flex";
}
```

Функция восстановления энергии (передается параметр размера начисляемого mp)
```
this.addMp = function(saze){        
    this.mp += saze;                
    if(this.mp > 100)               
        this.mp = 100;             
}
```
Функция перменешия игрока по координате Х
```
this.moveLeft = function(){
    if(!this.isDie){
        player.isRight = false; 
        player.isLeft = true;   
        if (this.drawX > gameWidth/4)
        this.drawX -= this.speed;                  
        if(this.drawX < 0) this.drawX = 0;        
        player.draw();                            // вызов функции отрисовки спрайта игрока при хотьбе
        if(fonposishio >=0)
          fonposishio-=4;
    }                         
}
```
Функции отрисовки спрайта игрока при хотьбе
```
Player.prototype.draw = function(){                                             
    clearCtxPlayer();                                                          
    this.srcX = (this.srcX === 300 ? 0 : this.srcX + 60);                       
    if(this.isRight)                                                                 
        persR.drawImage(gamerR, this.srcX, this.srcY, this.width, this.height,  
        this.drawX, this.drawY, this.width, this.height);                       
    if(this.isLeft)                                                                  
        persL.drawImage(gamerL, this.srcX, this.srcY, this.width, this.height,  
            this.drawX, this.drawY, this.width, this.height);                   
}   
```
Функция взоимодействия через клавиши
```
function chekKeyDown(e){                        
    var keyID = e.keyCode || e.which;           
    var keyChar = String.fromCharCode(keyID);  
    if(keyChar == "X"){  
        e.preventDefault();
        player.moveRight();
    }
    if(keyChar == "Z"){                        
        e.preventDefault();        
        player.moveLeft();              
    }
    if(keyChar == "N"){                         
        e.preventDefault();                     
        player.shout();
    }
    if(keyChar == "M"){                         
        e.preventDefault();                     
        player.hit();
    }
}
```
