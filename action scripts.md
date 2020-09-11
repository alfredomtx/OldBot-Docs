# Actions scripts
### alarme_ativar()
Realiza a mesma ação de quando o botão de Ativar Alarme é pressionado(após ter clicado no botão para Parar o alarme).
```c
alarme_ativar()
```

### clicar_sqm(`clique, direção, vezes, delay_cliques`)
* `param 1:`</i>  "Left" ou "Right"
* `param 2:`</i>  SO, S<b style="font-size: 12px"> \/, SE, O<span style="font-size: 12px"> <</span>, C(`char`), L<span style="font-size: 12px"> ></span>, NO, N<b style="font-size: 12px"> /\, NE
* `param 3:`</i> número
* `(opc) param 4:` número <sub><sup> intervalo em milisegundos após clicar, o padrão é 1000ms </sup></sub>
* `(opc) param 5:` número
