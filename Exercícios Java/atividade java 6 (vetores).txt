import java.util.Scanner;

public class ClassificaTriangulo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double lado1, lado2, lado3;

        System.out.print("Digite o comprimento do primeiro lado do triângulo: ");
        lado1 = scanner.nextDouble();

        System.out.print("Digite o comprimento do segundo lado do triângulo: ");
        lado2 = scanner.nextDouble();

        System.out.print("Digite o comprimento do terceiro lado do triângulo: ");
        lado3 = scanner.nextDouble();

        if (lado1 <= 0 || lado2 <= 0 || lado3 <= 0 || lado1 + lado2 <= lado3 || lado1 + lado3 <= lado2 || lado2 + lado3 <= lado1) {
            System.out.println("Triângulo não válido.");
        } else if (lado1 == lado2 && lado2 == lado3) {
            System.out.println("Triângulo equilátero.");
        } else if (lado1 == lado2 || lado1 == lado3 || lado2 == lado3) {
            System.out.println("Triângulo isósceles.");
        } else {
            // Verifica se é um triângulo retângulo usando o Teorema de Pitágoras
            if (Math.pow(lado1, 2) + Math.pow(lado2, 2) == Math.pow(lado3, 2) ||
                Math.pow(lado1, 2) + Math.pow(lado3, 2) == Math.pow(lado2, 2) ||
                Math.pow(lado2, 2) + Math.pow(lado3, 2) == Math.pow(lado1, 2)) {
                System.out.println("Triângulo retângulo.");
            } else {
                System.out.println("Triângulo escaleno.");
            }
        }

        scanner.close();
    }
}
