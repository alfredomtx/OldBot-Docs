



# Introdução
Action Scripts são utilizados para escrever um código para realizar diversas ações em sequência, sem a necessidade de criar 1 Waypoint para cada ação utilizando Special Actions.

Com isto, podemos agrupar ações que são comumente usadas repetitivamente em um único waypoint de Action Script, que conterá o código para realizá-las.
Inclusive algumas Action Scripts possuem ações/opções disponiveis para uso que Special Actions não possuem.

---

# Action Scripts
### alarme_ativar()
Realiza a mesma ação de quando o botão de Ativar Alarme é pressionado(`após ter clicado no botão para Parar o alarme`).
    

### alarme_parar()
Realiza a mesma ação de quando o botão de Parar Alarme é pressionado na tela do Painel do Cavebot.
    

### ativar_server_log()
Procura pela aba do chat do Server Log e clica para ativá-lonecessário para a função de lootear somente com loot valioso/pular loot vazio que precisa do Server Log visível.
    

### atualizar_posicao_char()
Realiza a função de detectar a posição central do char na tela e atualiza os valores, função compatível com **Tibia 11 e 12** somente.
    

### checar_lixos_dropar()
Realiza a mesma ação da Special Action "Checar lixos para dropar".
    

### check_disconnected_desabilitar()
Realiza a mesma ação da Special Action `Desabilitar check disconnected nas waypoints`.
    

### check_disconnected_habilitar()
Realiza a mesma ação da Special Action `Habilitar check disconnected nas waypoints`.
    

### clicar_sqm(`clique, direção, vezes, delay cliques`)
* `param 1:` "Left" ou "Right"
* `param 2:` SO, S `\/`, SE, O `<`, C`(char)`, L `>`, NO, N `/\`, NE
* `param 3:` número
* <sub><sup>(opc)</sup></sub> `param 4:` número <sub><sup> intervalo em milisegundos após clicar, o padrão é **1000ms** </sup></sub>
* <sub><sup>(opc)</sup></sub> `param 5:` número
```
clicar_SQM(Right, S, 1) 
```
> Clicar com o botão direito 1 vez no SQM ao Sul do char.
  
  
### clicar_na_imagem(`clique, vezes, diretório imagem, delay cliques, tolerância`)
* `param 1:` "Left" ou "Right"
* `param 2:` número
* `param 3:` diretório da imagem <sub><sup>  que deve estar **dentro da pasta** do script atual </sup></sub>
* <sub><sup>(opc)</sup></sub> `param 4:` número <sub><sup> intervalo em milisegundos após clicar, o padrão é **1000ms** </sup></sub>
* <sub><sup>(opc)</sup></sub> `param 5:` número <sub><sup> nível de tolerância, de 30 a 80, ao buscar pela imagem. Quanto menor mais preciso é a busca, o padrão é **45** </sup></sub>

``` 
clicar_na_imagem(Left, 1, 1000, WP1.png) 
```
>Exemplo 1: Clicar com o botão esquerdo 1 vez na imagem `WP1.png` que está na pasta do script.
``` 
clicar_na_imagem(Right, 3, 1000, imagens_script\meuitem.png) 
```
> Exemplo 2: Clicar com o botão direito 1 vez na imagem **`meuitem.png`** que está dentro da pasta **`imagens_script`** dentro da **pasta do script**.


### clicar_posicao_tela(`clique, x, y, vezes, delay cliques`)
* `param 1:` "Left" ou "Right"
* `param 2:` coordenada X da tela
* `param 3:` coordenada Y da tela
* `param 4:` número <sub><sup> intervalo em milisegundos após clicar, o padrão é **1000ms** </sup></sub>
```
clicar_posicao_tela(Right, 1250, 350, 5) 
```
> Clicar com o botão direito 5 vezes na posição `x:1250`, `y:350` da tela.

### depositar_itens()
Realiza a ação da Special Action `Procurar depot vazio e depositar itens`, os itens a serem depositados e backpacks devem estar todos configurados préviamente em algum waypoint dessa ação.

### enviar_mensagem(`mensagem`)
* `param 1:` texto
```
enviar_mensagem(hi)
```
> Escrever e enviar a mensagem `hi` no jogo.

### executar_ahk_script(`nome script, aguardar_execução`)
* `param 1:` texto
* <sub><sup>(opc)</sup></sub> `param 2:` 0 ou 1
	* (`verdadeiro/falso`) o padrão é 0. Se o valor for 1, irá aguardar o processo do AHK Script ser fechado para seguir para a próxima ação.
```
executar_ahk_script(`start ring refill v1.1`)
```
> executar o AHK Script "start ring refill v1.1".


### exitar_jogo(`tirar_screenshot`)
* <sub><sup>(opc)</sup></sub> `param 1:` 0 ou 1
	* (`verdadeiro/falso`) o padrão é 1. Se 1, irá tirar uma screenshot da tela antes de exitar o jogo.


### esperar(`milisegundos`)
* `param 1:` número
```
esperar(300)
```
> Realizar um "Sleep" de 300ms.



### fechar_cavebot()
Fechar o "executável" do Cavebot, o que irá parar o Cavebot/Targeting e precisará ser reaberto novamente. 
Útil para fazer validações no script e impossibilitar o uso do script caso alguma validação não esteja correta.

 
### intervalo_andar_waypoint(`milisegundos`)
* `param 1:` número
```
intervalo_andar_waypoint(3000)
```
> Alterar o tempo de checagem do waypoint(intervalo andar waypoint) para `3000ms`.

### ir_para_waypoint(`waypoint, abortar ações`)
* `param 1:` número
* <sub><sup>(opc)</sup></sub> `param 2:` 0 ou 1
	* se for 1, irá abortar próximas as ações do Action Script e ir para o Waypoint, o padrão é 1
```
ir_para_waypoint(1)
```
> Ir para o waypoint 1. **Atenção** ao colocar mais de 1 dessa ação no mesmo Action Script, pois o waypoint será o setado pela última executada.


### ir_para_label(`label, abortar ações`)
* `param 1:` texto
* <sub><sup>(opc)</sup></sub> `param 2:` 0 ou 1
	* se for 1, irá abortar próximas as ações do Action Script e ir para o Label, o padrão é 1
```
ir_para_label(comprar_supply)
```
> Ir para o label "comprar_supply". **Atenção** ao colocar mais de 1 dessa ação no mesmo Action Script, pois o waypoint será o setado pela última executada.


### looter_desabilitar()
Realiza a mesma ação da Special Action "Desabilitar Looter".


### looter_habilitar()
Realiza a mesma ação da Special Action "Habilitar Looter".


### luring_mode_iniciar(`quantidade monstros`)
* `param 1:` número
	* quantidade mínima de monstros no Battle List para começar a atacar
```
luring_mode_iniciar(3)
```
> Iniciar o Luring Mode e parar para atacar somente quando houver 3 monstros ou mais no Battle List.


### luring_mode_parar()
> Parar o Luring Mode e voltar a atacar normalmente.
    

### message_box(`mensagem`)
Realiza a mesma ação da Special Action `Mostrar MessageBox na tela`.
* `param 1:` texto
```
message_box(`você está usando o OldBot`)
```
> Mostrar uma MessageBox na tela escrito `você está usando o OldBot`.


### mouse_move(`x, y`)
* `param 1:` coordenada X da tela
* `param 2:` coordenada Y da tela
```
mouse_move(150, 200)
```
> Mover o mouse até a posição x:150, y:200 na tela.


### mouse_drag(`x1, y1, x2, y2, vezes`)
* `param 1:` coordenada X da tela
* `param 2:` coordenada Y da tela
* `param 3:` coordenada X da tela
* `param 4:` coordenada Y da tela
* <sub><sup>(opc)</sup></sub> `param 5:` número <sub><sup> quantidade de vezes para repetir a ação, o padrão é 1 vez </sup></sub>
```
mouse_drag(150, 200, 650, 350) 
```
>Clicar com o botão esquerdo na posição `x:150, y:200` e arrastar o mouse até a posição `x:650, y:350` na tela.


### mouse_drag_imagem(`diretório imagem origem, diretório imagem destino, vezes, tolerância`)
* `param 1:` diretório da imagem <sub><sup>  que deve estar **dentro da pasta** do script atual </sup></sub>
* `param 2:` diretório da imagem <sub><sup>  que deve estar **dentro da pasta** do script atual </sup></sub>
* <sub><sup>(opc)</sup></sub> `param 3:` número <sub><sup> quantidade de vezes para repetir a ação, o padrão é 1 vez </sup></sub>
* <sub><sup>(opc)</sup></sub> `param 5:` número <sub><sup> nível de tolerância, de 30 a 80, ao buscar pela imagem. Quanto menor mais preciso é a busca, o padrão é **45** </sup></sub>
```
mouse_drag_imagem(`diamond_arrow.png, minha_backpack.png, 10`) 
```
> Realizar 10 vezes a ação de buscar pela imagem `diamond_arrow.png` na tela, se encontrada, clicar e mover(arrastar) para a posição da imagem `minha_backpack.png`. Resumidamente, mover a Diamond Arrow para a Backpack.


### monstro_adicionar_lista_atacar(`nome_monstro, hotkey_magia`)
* `param 1:` nome do monstro
	* O monstro deve estar cadastrado na **lista geral dos monstros**`(Cavebot\monstros.ini)` na tela do Targeting
* `param 2:` tecla <sub><sup> hotkey da magia para usar ao atacar esse monstro, **será pressionada a cada 2 segundos** </sup></sub>
```
monstro_adicionar_lista_atacar(adventurer, F1) 
```
> Adicionar o monstro `adventurer` na lista dos monstros para ser atacado pelo Targeting, utilizando a magia da hotkey `F1`.


### monstro_remover_lista_atacar(`nome_monstro`)
* `param 1:` nome do monstro
	* O monstro deve estar cadastrado na **lista geral dos monstros**`(Cavebot\monstros.ini)` na tela do Targeting
```
monstro_remover_lista_atacar(adventurer) 
```
> Remover o monstro `adventurer` da lista dos monstros para serem atacados pelo Targeting(da lista do script).


### pressionar_tecla(`tecla, vezes,  delay`)
* `param 1:` tecla - <a href="https://www.autohotkey.com/docs/commands/Send.htm#keynames" target="_blank">lista de teclas</a>
* `param 2:` número 
* `param 3:` número <sub><sup> intervalo em milisegundos após clicar, o padrão é **250ms**</sup></sub>
##### Exemplos:
```      
pressionar_tecla(Up, 3)
```
> Pressionar a `seta para cima` 3 vezes
```
pressionar_tecla(Esc, 1)
```
> Pressionar a tecla `Esc` 1 vez.
```
pressionar_tecla(Enter)
```
> Pressionar a tecla `Enter` 1 vez.
```
pressionar_tecla(a, 5)
```
> Pressionar a tecla "a" 5 vezes.


### reabrir_cavebot()
Similar a action `fechar_cavebot()`, porém ao invés de fechar irá reabrir o "executável" do Cavebot/Targeting. É a mesma ação do botão de `Reload` do painel do Cavebot.


### targeting_desabilitar()
Realiza a mesma ação da Special Action `Desabilitar Targeting`.
 
 
### targeting_habilitar()
Realiza a mesma ação da Special Action `Habilitar Targeting`.
    

### variavel_setar_valor(`nome_variável, valor`)
* `param 1:` nome da variável
	*  [ ] pendente criação de documentação das variáveis
* `param 2:` valor da variáver **`sem $`**
```
variavel_setar_valor(AntiKS, 1) 
```
> Muda o valor da variável `AntiKS` para `1`, ativando a função de AntiKS do bot.
```
variavel_setar_valor(quantidade_potions_comprar, 250) 
```
> Muda o valor da variável(do script) `quantidade_potions_comprar` para `250`.


### virar_char_direcao(`direção`)
* `param 1:` S `\/`, O `<`, L `>`, N `/\`
```
virar_char_direcao(S)
```
> Virar o char para a direção Sul.


### zoom_minimapa(`zoom`)
* `param 1:` número de `1` a `4`
```
zoom_minimapa(4)
```
> Alterar o zoom do minimapa para o nível 4.


---

# Condições nas Action Scripts
Condições também podem ser utilizadas em cada Action Script:

### se cap for menor que(`quantidade, abortar ações*`)
* `param 1:` número
```
message_box(cap abaixo do selecionado) [se cap for menor que (50)] 
```
> Exibir uma MessageBox escrito `"cap abaixo do selecionado"` se a o cap for menor que `50`.

    

### se potion for menor que(`nome da potion, quantidade, abortar ações*`)
* `param 1:` nome da potion
	* deve ser uma das potions disponíveis na condição de potion na tela de Special Action
* `param 2:` número
```
message_box(poucas potions) [se potion for menor que (strong mana potion, 25)] 
```
> Exibir uma MessageBox escrito `"poucas potions"` se a quantidade de strong mana potion for menor que `25`.


### se supply for menor que(`nome do item, quantidade, abortar ações*`)
* `param 1:` nome do item
	* deve ser uma dos itens disponíveis na condição de supply na tela de Special Action
* `param 2:` número
```
message_box(poucas munições) [se supply for menor que (crystalline arrow, 120)] 
```
> Exibir uma MessageBox escrito `"poucas munições"` se a quantidade de crystalline arrow for menor que `120`.


### se imagem for localizada(`diretório imagem, abortar ações*`)
* `param 1:` diretório da imagem `.png` ou `.jpg` <sub><sup>  que deve estar **dentro da pasta** do script atual </sup></sub>
```
message_box(imagem localizada!) [se imagem for localizada (imageminimigo.png)] 
```
> Exibir uma MessageBox escrito `"imagem localizada!"` se a imagem `"imageminimigo.png"` for localizada na tela.


### se imagem não for localizada(`diretório imagem, abortar ações*`)

* `param 1:` diretório da imagem `.png` ou `.jpg` <sub><sup>  que deve estar **dentro da pasta** do script atual </sup></sub>
```
message_box(imagem não localizada!) [se imagem for localizada (meuitem.png)] 
```
> Exibir uma MessageBox escrito `"imagem não localizada!"` se a imagem `"meuitem.png"` não for localizada na tela.


### se a variável for(`nome variável, operador, valor, abortar ações*`)
* `param 1:` nome da variável **`sem $`**
* `param 2:` "menor", "maior", "igual" ou "diferente"
* `param 3:` valor da variável
```
message_box(AntiKS desligado) [se a a variável for (AntiKS, diferente, 1)] 
```
> Exibir uma MessageBox escrito `"AntiKS desligado"` se a variável `AntiKS` for `diferente de 1`.


### se o floor for(`nível do floor, operador, abortar ações*`)
* `param 1:` nível do floor a ser checado
	* de `-8` a `7`, sendo `0` o térreo
* `param 2:` "igual" ou "diferente"
```
message_box(Está no subsolo -1) [se o floor for (-1, igual)] 
```
> Exibir uma MessageBox escrito `"Está no subsolo -1"` se o floor(nível do solo no tibia) for `igual a -1`.
```
message_box(Não está no térreo) [se o floor for (0, diferente)] 
```
> Exibir uma MessageBox escrito `"Não está no térreo"` se o floor(nível do solo no tibia) for `diferente de 0`.

## `PARÂMETRO "abortar ações*"`
Opcional em todas as condições, pode ser  **`0` ou `1`**.
Se marcado como 1, irá abortar todas as próximas ações do Action Script se a **condição der como verdadeira**, o padrão é `0`.

---

# Informações extras:
Variáveis `do script` também podem ser utilizadas para definir valor de cada parâmetro de todas as funções:
```
pressionar_tecla($hotkey_machete, 1) 
```
> Pressionar 1 vez a hotkey configurada na variável `$hotkey_machete`
```
clicar_sqm($clique, $sqm_clicar, $vezes_clicar_sqm) 
```
> Clicar com o botão do mouse configurado na variável `$clique` no sqm `$sqm_clicar`, repetir a ação `$vezes_clicar_sqm` vezes.

---

# Regras de criação de Action Script:
1. Seguir o formato em minúsculo ao escrever o nome das funções.
2. Se a função possui mais de um parâmetro, cada parâmetro deve ser separado por vírgula(`,`).
3. Para escrever um comentário, iniciar a linha com hashtag(`#`)
4. A condição deve ser no mesmo modelo em que é colocada na linha ao selecionar uma condição na lista - após a action, entre chaves `[]` e com os valores dentro de parênteses `()`.
5. Não pode haver espaço a esquerda do primeiro parâmetro da função:
	> Exemplo **correto**: `pressionar_tecla(Down, 2)`
	>
	> Exemplo **incorreto**: `pressionar_tecla( Down, 2)` - espaço a esquerda do `Down`.

---

## Video tutorial sobre Action Scripts:
https://youtu.be/hIAMXvCMpVQ

