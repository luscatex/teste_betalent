# Plano de Testes
Esse arquivo contém informações sobre os cenários e casos de testes para a plataforma [Sauce Demo](https://www.saucedemo.com/)

Ferramentas utilizadas durante os testes: Navegador Chrome e ShareX para captura de telas.

## Cenários de Testes
 1. Login
 
    1.1 Logar com todos os tipos de usuário.

	1.2 Logar com usuário correto e senha incorreta.

	1.3 Logar com senha correta e usuário incorreto.

    1.4 Logar com os campos de usuário e senha vazios.


2. Ordenação e filtragem de produtos

	2.1 Ordenar produtos por todos os filtros disponíveis. 
	
3. Fluxo de compra

	3.1 Realizar uma compra com um item ou mais no carrinho

	3.2 Tentar realizar uma compra sem itens no carrinho.

4.  Remoção de itens do carrinho

5. Navegação entre páginas

6. Logout 


## Casos de teste

**Login**
 Número|Caso|Critério de Sucesso|Status|
|------|------| --------| --------|
| 01   |Realizar o login preenchendo os campos login e senha com dados corretos|Acessar a plataforma|Aprovado|
| 02   |Realizar o login preenchendo os campos login e senha com dados incorretos|Sistema informar que os dados inseridos estão incorretos|*Erro de UI encontrado*|
| 03   |Tentar realizar o login sem preencher os campos login e senha|Sistema informar que é necessário preencher os campos para logar|Aprovado|


**Ordenação e filtragem de produtos**
 Número|Caso|Critério de Sucesso|Status|
|------|------| --------| --------|
| 01   |Ordenar produtos por ordem alfabética|Produtos serem exibidos ordenados corretamente pela ordem alfabética|*Erro ocorrendo com usuário específico*|
| 02   |Ordenar produtos por ordem alfabética inversa|Produtos serem exibidos ordenados corretamente pela ordem inversa do alfabeto|*Erro ocorrendo com usuário específico*|
| 03   |Ordenar produtos do preço mais baixo ao mais alto|Produtos com preços mais baixos serem exibidos corretamente em primeiro|*Erro ocorrendo com usuário específico*|
| 04   |Ordenar produtos do preço mais alto ao mais baixo|Produtos com preços mais altos serem exibidos corretamente em primeiro|*Erro ocorrendo com usuário específico*|

**Fluxo completo de compras**
 Número|Caso|Critério de Sucesso|Status|
|------|------| --------| --------|
| 01   |Inserir um item no carrinho de compras|Item deve ser exibido na página do carrinho com todas os dados corretos|*Erro ocorrendo com usuário específico*|
| 02   |Realizar uma compra após inserir um item ou mais no carrinho de compras|Após inserir os itens no carrinho e clicar no botão "Checkout" o usuário deve ser direcionado para uma tela que exige o preenchimento dos dados de envio.|Aprovado|
| 03   |Preencher dados de envio exigidos no processo de compra|Plataforma deve informar que todos os dados de envio são obrigatórios.|*Erro de UI encontrado*|
| 04   |Verificar dados da compra realizada|Após preencher os dados de envio, a plataforma deve exibir os dados dos itens selecionados para compras corretamente. Como valor total dos itens, de frete e a soma dos dois representando o total da compra.|*Erro*|
| 05   |Finalizar uma compra|Ao clicar no botão "Finish" e finalizar uma compra o usuário deve ser direcionado para uma tela agradecendo o pedido realizado.|*Erro ocorrendo com usuário específico*|
| 06   |Remover um item do carrinho de compras|O item removido deve voltar ao estoque e ficar selecionado para compra novamente.|*Erro ocorrendo com usuário específico*|
| 07   |Tentar realizar uma compra sem itens no carrinho|O sistema não deve permitir que o usuário realize o processo de compra sem nenhum item no carrinho|*Erro*|

**Logout**
 Número|Caso|Critério de Sucesso|Status|
|------|------| --------| --------|
| 01   |Realizar o logout da plataforma|Usuário deve ser deslogado da plataforma e redirecionado a página de login.|Aprovado|
| 02   |Realizar um login com o mesmo usuário que realizou um logout recentemente|Usuário conseguir logar novamente na plataforma.|Aprovado|
| 03   |Tentar acessar alguma página da plataforma estando deslogado|Ao tentar através da url acessar uma página da plataforma, o usuário deve ser direcionado para a página de login.|*Erro de UI encontrado*|

## Relatório de erros
Informação e descrição sobre os erros encontrados durante os testes realizados. 

Antes de relatar alguns erros é importante informar sobre o problemas de performance que ocorrem na plataforma com o usuário *performance_glitch_user*. Também vale reportar que muitos erros e bugs foram encontrados durantes testes realizados com os usuários *error_user* e *problem_user*.

**Login**

Erro de UI na mensagem que informa que usuário e senha não foram encontrados no sistema após inserir uma senha errada.
![](https://i.ibb.co/J2Q9L3d/login-02.png)
*Sugestão de melhoria*: Por questão de segurança o ideal seria apenas informar que algum dos campos, senha ou usuário, está incorreto.

**Ordenação e filtragem de produtos**

Erro na funcionalidade de ordenar os itens de todas as maneiras disponíveis no sistema.
![](https://i.ibb.co/48q2Rf7/error-user-sroting.png)


**Fluxo completo de compras**

Erro de funcionalidade ao tentar adicionar um item no carrinho utilizando o usuário *error_user*
![](https://i.ibb.co/pdPMvYp/error-user-adicionar-item.png)

Erro de UI na tela de preenchimento de dados de envio. Mesmo após preencher os dados obrigatórios, o campo fica com um underline vermelho e ícone de erro.
![](https://i.ibb.co/0ZkcyvS/ui-campo-name.png)

Erro na funcionalidade que exibe o valor da compra para o usuário. Valor total dos itens exibiu mais de dois números após a vírgula.
![](https://i.ibb.co/mTVpXZL/compras-04.png)

Não foi possível finalizar uma compra com o usuário *error_user*
![](https://i.ibb.co/3hvRkd6/error-user-finalizar-compra.png)

Erro exibido em console ao tentar remover o item de um carrinho na conta do usuário *error_user*
![](https://i.ibb.co/M75qMcr/error-user-remover-item.png)

Foi possível finalizar uma compra com o carrinho sem nenhum item
![](https://i.ibb.co/WtSz9tG/compras-07-1.png)
![](https://i.ibb.co/wMS3Z6T/compras-07-2.png)

**Logout**

Erro de UI na mensagem que informa que uma página do sistema só pode ser acessada logada.
![](https://i.ibb.co/KXTYDw7/logout-03.png)

Foram encontrados alguns erros de navegação e de responsividade.

Ao tentar acessar a página About com o usuário *problem_user*, fui direcionado para um página 404
![](https://i.ibb.co/x57Jk0G/problem-user-about.png)

Ao tentar visualizar a plataforma emulando o acesso por um dispositivo móvel, existe um espaçamento muito grande entre a descrição do item e seu valor.
![](https://i.ibb.co/zh9mc8G/chrome-Krusy-LQX2-Z.png)
![](https://i.ibb.co/mCs5fjH/chrome-s1nzi9-X98c.png)
