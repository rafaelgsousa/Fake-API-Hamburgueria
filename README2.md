#API DA HAMBURGUERIA

-A baseurl é https://hamburgueriarafael2.herokuapp.com.

1.CAMPO USUÁRIO:
-Local onde são feitos os signup e login.

-Os endpoints são:
*SIGNUP:
-post
-baseurl/signup
-body
exemplo:
{
    "name":"johndoo",
    "email":"johndoo@gmail.com",
    "password":"123456"
}
*LOGIN:
-post
-baseurl/login
-body
exemplo:
{
    "email":"johndoo@gmail.com",
    "password":"123456"   
}

2.CAMPO CATÁLOGO:
-Local para captura dos dados dos itens do menu.
-Os endpoints são:
*REGISTER MENU:
Obs: Esse endpoint não é liberado no sistema disponivel para
clientes.
-post
-baseurl/menu
-body
exemplo:
{
	"name":"Sunday OvoMaltine",
	"category":"Sobremsas",
	"img":"https://s3-alpha-sig.figma.com/img/33b4/26ec/3ddbebe1535caac9b2a02d00b60bff97?Expires=1636934400&Signature=UVRfKXyRojXuDxUCIXYW3diJhH7Y8-yQWHPj3r~1qboZVEnZKlYLyA-aB4OdHAXKSkmYlmv5wgqykTN5tVCCRmrNS8~sl8tIxQLSmes2zqaDkty016W1AhrfqWKHjzfpS8jqEkXbxCICUeRrRKdaj0vbTGy4br5xIV15teeBu9q2QucV2a8x3OPwg4c93FDEqot-txx8sHWSOszdDE9RYfRsN5VzMkRDkVePBsHf7wk7DoUeCJF4nRdRcxJWxx3zFX7pn2jNjcrojorMUU3WTr6bnevOYHZCdWir8oB5MCdntJSzVwa4iiWqD3ugTRSCPqoqDMe~ii5zkT22pLP7Mg__&Key-Pair-Id=APKAINTVSUGEWH5XD5UA",
	"price": 10.00,
	"userId": 2
}

-autorização tipo Bearer
exemplo:
{
    headers: {
         Authorization: `Bearer ${token}`,
    }
}


*CATÁLOGO MENU:
-Usada para capturar todos os itens do catálogo.
-get
-baseurl/menu?page=(numero da página)


3.CART/CARRINHO:
-Local liberado somente para pessoas logadas pois precisará do token.
-Os endpoints são:
*REGISTER PRODUCTS.
-post
-baseurl/cart
-body
exemplo:
{
    "name": "X-burguer",
    "category": "Sanduiche",
    "price": 3,
    "userId": 4
}
-autorização tipo Bearer
exemplo:
{
    headers: {
         Authorization: `Bearer ${token}`,
    }
}

*MY CART:
-Usado para captura dos itens do cart/carrinho.
-get
-baseurl/cart/?userId=(numero do id do usuário)
-body
exemplo:
-autorização tipo Bearer
exemplo:
{
    headers: {
         Authorization: `Bearer ${token}`,
    }
}

*MY PERFIL CART:
-Usando para pegar informação do perfil do usuário e do seu cart/carrinho.
-get
-baseurl/users/(id do usuário)?_embed=menu
-autorização tipo Bearer
exemplo:
{
    headers: {
         Authorization: `Bearer ${token}`,
    }
}

*DELETE PRODUCT CART:
-Usando para tirar itens co carrinho registrados pelo cliente
-delete
-baseurl/cart/(id do iten no cart)
-autorização tipo Bearer
exemplo:
{
    headers: {
         Authorization: `Bearer ${token}`,
    }
}






