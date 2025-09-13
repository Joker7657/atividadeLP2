import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

class Item {
    private String nome;
    private double preco;

    public Item(String nome, double preco) {
        this.nome = nome;
        this.preco = preco;
    }

    public String getNome() {
        return nome;
    }

    public double getPreco() {
        return preco;
    }
}

class Pedido {
    private static int contador = 0;
    private int numero;
    private String cliente;
    private List<Item> itens;

    public Pedido(String cliente) {
        this.cliente = cliente;
        this.numero = ++contador;
        this.itens = new ArrayList<>();
    }

    public void adicionarItem(Item item) {
        itens.add(item);
    }

    public int getNumero() {
        return numero;
    }

    public String getCliente() {
        return cliente;
    }

    public List<Item> getItens() {
        return itens;
    }

    public double getTotal() {
        double total = 0;
        for (Item item : itens) {
            total += item.getPreco();
        }
        return total;
    }
}

public class RestauranteSaborCaseiro {
    private static List<Pedido> pedidos = new ArrayList<>();
    private static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int opcao;
        do {
            System.out.println("\n=== Menu Principal ===");
            System.out.println("1. Registrar Pedido");
            System.out.println("2. Remover Pedido");
            System.out.println("3. Listar Pedidos");
            System.out.println("4. Sair");
            System.out.print("Escolha uma opção: ");
            opcao = scanner.nextInt();
            scanner.nextLine(); // Limpar o buffer

            switch (opcao) {
                case 1:
                    registrarPedido();
                    break;
                case 2:
                    removerPedido();
                    break;
                case 3:
                    listarPedidos();
                    break;
                case 4:
                    System.out.println("Saindo...");
                    break;
                default:
                    System.out.println("Opção inválida!");
            }
        } while (opcao != 4);
    }

    private static void registrarPedido() {
        System.out.print("Nome do cliente: ");
        String nomeCliente = scanner.nextLine();

        Pedido pedido = new Pedido(nomeCliente);

        boolean adicionarMais = true;
        while (adicionarMais) {
            System.out.print("Nome do item: ");
            String nomeItem = scanner.nextLine();
            System.out.print("Preço do item: ");
            double precoItem = scanner.nextDouble();
            scanner.nextLine(); // Limpar o buffer

            Item item = new Item(nomeItem, precoItem);
            pedido.adicionarItem(item);

            System.out.print("Deseja adicionar mais itens? (s/n): ");
            String resposta = scanner.nextLine();
            if (resposta.equalsIgnoreCase("n")) {
                adicionarMais = false;
            }
        }

        pedidos.add(pedido);

        // Exibir nota de confirmação
        System.out.println("\n========================================");
        System.out.println("      Restaurante Sabor Caseiro      ");
        System.out.println("========================================");
        System.out.println("Pedido N°: " + pedido.getNumero());
        System.out.println("Cliente: " + pedido.getCliente());
        System.out.println("----------------------------------------");
        System.out.println("Itens:");
        for (Item item : pedido.getItens()) {
            System.out.println("- " + item.getNome() + " R$ " + item.getPreco());
        }
        System.out.println("----------------------------------------");
        System.out.println("Total: R$ " + pedido.getTotal());
        System.out.println("========================================");
        System.out.println(" Obrigado pela preferência! :) ");
        System.out.println("========================================\n");
    }

    private static void removerPedido() {
        System.out.print("Número do pedido a ser removido: ");
        int numero = scanner.nextInt();
        scanner.nextLine(); // Limpar o buffer

        boolean encontrado = false;
        for (Pedido pedido : pedidos) {
            if (pedido.getNumero() == numero) {
                pedidos.remove(pedido);
                encontrado = true;
                System.out.println("Pedido removido com sucesso!");
                break;
            }
        }

        if (!encontrado) {
            System.out.println("Pedido não encontrado!");
        }
    }

    private static void listarPedidos() {
        if (pedidos.isEmpty()) {
            System.out.println("Nenhum pedido registrado.");
            return;
        }

        for (Pedido pedido : pedidos) {
            System.out.println("\n========================================");
            System.out.println("Pedido N°: " + pedido.getNumero());
            System.out.println("Cliente: " + pedido.getCliente());
            System.out.println("----------------------------------------");
            System.out.println("Itens:");
            for (Item item : pedido.getItens()) {
                System.out.println("- " + item.getNome() + " R$ " + item.getPreco());
            }
            System.out.println("----------------------------------------");
            System.out.println("Total: R$ " + pedido.getTotal());
            System.out.println("========================================");
        }
    }
}
