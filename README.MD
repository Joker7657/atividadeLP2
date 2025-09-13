Descrição do Problema
Um restaurante (você escolhe o nome) precisa de um software para gerenciar os pedidos
recebidos. O sistema deve ser capaz de registrar novos pedidos, remover pedidos existentes
e listar todos os pedidos ativos de forma organizada.
Para modelar o sistema, você deverá criar classes que representem as entidades principais. A
classe Pedido deve conter atributos como número de identificação, nome do cliente e uma
lista de objetos do tipo Item. A classe Item, por sua vez, deve ter atributos para nome e preço.
A relação onde um objeto Pedido 'possui' uma lista de objetos Item é a representação prática
do conceito de Composição.
Requisitos Funcionais
O sistema deverá ser executado via console e apresentar um menu principal com as seguintes
opções:
1. Registrar Pedido:
○ O sistema deve solicitar o nome do cliente.
○ Um número de pedido deve ser gerado automaticamente de forma sequencial (1, 2,
3, ...).
○ O sistema deve permitir que o usuário adicione um ou mais itens ao pedido. Para
cada item, deve-se solicitar o nome e o preço.
○ Ao final, o pedido completo deve ser armazenado na estrutura de dados principal.
○ Após o registro, o sistema deve exibir uma nota de confirmação com o resumo do
pedido recém-criado (número do pedido, cliente, itens e valor total).
2. Remover Pedido:
○ O sistema deve solicitar o número do pedido que o usuário deseja remover.
○ Caso o pedido exista, ele deve ser removido da lista. Caso contrário, uma mensagem
de erro deve ser exibida.
3. Listar Pedidos:
○ O sistema deve exibir todos os pedidos registrados.
○ A exibição deve ser ordenada crescentemente pelo número do pedido.
○ Para cada pedido, devem ser mostradas todas as informações:
■ Número do Pedido
■ Nome do Cliente
■ Lista de Itens (com nome e preço de cada um)
■ Valor total do pedido (calculado dinamicamente pela soma dos preços de seus
itens).
4. Sair:
○ Encerra a execução do programa.
Requisitos Técnicos Obrigatórios
Para a implementação, você deve utilizar os seguintes conceitos:
● Linguagem: Java.
● Orientação a Objetos:
○ Classes e Objetos: Você deve criar, no mínimo, as classes Pedido e Item.
Recom-enda-se também criar uma classe principal (ex: Restaurante ou Sistema) que
conterá a lógica principal do programa, incluindo o menu e a lista de pedidos.
○ Composição: Aplicar o conceito de composição. A classe Pedido deve ser composta
por objetos da classe Item.
● Estrutura de Dados: Utilizar ArrayList ou LinkedList para armazenar a lista de pedidos.
● Controle de Fluxo: O menu principal de interação com o usuário deve ser implementado
utilizando a estrutura switch-case, o uso de While para que o menu continue rodando
após as operações.
● Interface: A interação com o usuário deve ser realizada via console (utilizando a classe
Scanner).
Instruções de Entrega
1. Crie um repositório no GitHub para desenvolver a atividade. É uma boa prática manter o
histórico de suas alterações através de commits.
2. Em breve, abrirei o portal para submissão da tarefa no SIGAA.
3. Para a entrega, você poderá submeter o link do seu repositório do GitHub ou um arquivo
.zip contendo todos os arquivos .java do seu projeto.
Ajudinha do Prof:
Para a funcionalidade de "Registrar Pedido", após a sua conclusão, você deve exibir um
resumo formatado. Abaixo está um modelo de como você pode estruturar essa saída no
console usando System.out.println(). Sinta-se à vontade para adaptar e melhorar!
// Exemplo de como printar a nota fiscal no console
System.out.println("\n========================================");
System.out.println(" Restaurante (Nome que você quiser) ");
System.out.println("========================================");
System.out.println("Pedido N°: " + numeroDoPedido);
System.out.println("Cliente: " + nomeDoCliente);
System.out.println("----------------------------------------");
System.out.println("Itens:");
// Aqui você faria um loop para percorrer os itens do pedido
for (Item item : listaDeItensDoPedido) {
// Usamos o '+' para juntar o texto com as variáveis do item
System.out.println("- " + item.getNome() + " R$ " + item.getPreco());
}
System.out.println("----------------------------------------");
// O valor total deve ser calculado
System.out.println("Total: R$ " + valorTotal);
System.out.println("========================================");
System.out.println(" Obrigado pela preferência! :) ");
System.out.println("========================================\n");
Bom trabalho!
