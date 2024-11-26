# Plano de Testes da API restful-booker
Documento descrevendo os cenários de testes realizados na API [Restful-booker](https://restful-booker.herokuapp.com/apidoc/index.html) e os resultados obtidos. No repositório deste projeto existe um arquivo de collection em JSON que possue todas as requisições cujos testes foram realizados. 

Ferramenta utilizada nos testes: Postman

## Cenários de Testes

 1. Autenticação
 
    1.1 Gerar token de autenticação.

	1.2 Tentar gerar token com credenciais inválidas.

2. Gestão de reservas

	2.1 Listar todas as reservas.
    2.2 Buscar uma reserva específica. 
    2.3 Criar uma nova reserva. 
    2.4 Atualizar uma reserva existente. 
    2.5 Deletar uma reserva. 
	
3. Filtros e buscas

	3.1 Buscar reservas por data de check-in

	3.2 Buscar reservas por data de check-out.

## Resultados obtidos

Autenticação - CreateToken
 
Token de autenticação gerado com sucesso.
![alt text](https://i.ibb.co/nwsGgTs/Postman-FO4-NSYgj-Qj.png)

Token não é gerado quando algum dado de credencial está incorreto.
![](https://i.ibb.co/7VhVkdJ/Postman-D1s2-Vn9h-JP.png)
 
 
Filtros e buscas de reservas - GetBookingIds e GetBooking

Lista com todas as reservas.
![](https://i.ibb.co/sbfJ3bm/Postman-7myh5-T6-Ap-N.png)

Resultado de busca de uma reserva específica.
![](https://i.ibb.co/BjVTtBN/Postman-Zrih-Pp-CT2-B.png)

Resultado da busca por uma reserva cujo ID não existe.
![](https://i.ibb.co/Vqd3qFf/Postman-am-BOINZQw-D.png)

Resultado ao filtrar a busca por nome e sobrenome na reserva.
![](https://i.ibb.co/2WSwHXL/Postman-Or-KBh5w-AUd.png)

Resultados ao filtrar a busca de uma reserva pela data de check-in e check-out.
![](https://i.ibb.co/2hNgktP/Postman-h-FX5zv0-BDp.png)
![](https://i.ibb.co/nfdJTym/Postman-s-BDO6-QS2-Af.png)

Gestão de reservas - CreateBooking, UpdateBooking e DeleteBooking

Criação de Reservas
Criando reserva através das requisições na API e demonstrado nos prints 2 e 3 que é possível encontrá-la por busca.
![](https://i.ibb.co/y8LpgQT/Postman-q-SZEtp-Tao-G.png)
![](https://i.ibb.co/bF3qbyF/Postman-Bxtg5-NPe-X2.png)
![](https://i.ibb.co/3hQxrMP/Postman-u-QUybs-F6u-G.png)

Atualizar uma reserva existente.

Nova reserva criada
![](https://i.ibb.co/fqj6NkJ/Postman-f-Neljv-Fy-Gn.png)

Reserva criada com informações das datas atualizadas.
![](https://i.ibb.co/nwbtP3V/Postman-9i-G6-Vg-Qs-V9.png)

Deletar uma reserva.
![](https://i.ibb.co/9rgG07z/Postman-q0y4-Wr6-WQm.png)
![](https://i.ibb.co/6tL86XY/Postman-Lp-Al-IU1-ZPT.png)

## Relatório de erros
Foi possível criar uma reserva sem nenhum dos dados preenchidos na requisição.
![](https://i.ibb.co/Y7WCRn7/Postman-QNu-GNq1-N86.png)
![](https://i.ibb.co/gyprgqk/Postman-Gck-Hnful0i.png)

API retornou o código 405 ao tentar atualizar e deletar a reserva que foi criada sem dados válidos.
![](https://i.ibb.co/4VYNKSj/image.png)
![](https://i.ibb.co/dc7X3VK/image.png)

Erro nos campos de checkin e checkout ao inserir as datas no formato padrão.
![](https://i.ibb.co/gRT5hjF/image.png)