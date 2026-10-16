import java.util.Scanner;

public class Frete {
    private CalculadoraFrete transportadora;

    Frete(CalculadoraFrete transportadora){
        this.transportadora = transportadora;
    }
    public double calcularFrete (double peso, double distancia){
        return transportadora.calcular(peso, distancia);
    }
}
interface CalculadoraFrete {
    double calcular(double peso, double distancia);
}


class CalculadoraFreteSedex implements CalculadoraFrete{
    public double calcular (double peso, double distancia){
        return peso * distancia;
    }
}

class CalculadoraFreteJadlog implements CalculadoraFrete {
    public double calcular(double peso, double distancia){
        return peso + distancia;
    }
}

class CalculadoraFreteAzul implements CalculadoraFrete{
    public double calcular(double peso, double distancia){
        return peso * peso + distancia;
    }
}

class Main {
    public static void main(String[] args) {

        Frete calculadora;

        Scanner sc = new Scanner(System.in);

        System.out.println("Digite o peso: ");
        double peso = sc.nextDouble(); 

        System.out.println("Digite a distancia: ");
        double distancia = sc.nextDouble();

        
        System.out.println("Escolha sua transportadora: ");
        System.out.println("1 - Sedex");
        System.out.println("2 - Jadlog");
        System.out.println("3 - Azul");

        int opcao = sc.nextInt();
        double resultado = 0;
        switch (opcao){
            case 1:
                calculadora = new Frete(new CalculadoraFreteSedex());
                resultado = calculadora.calcularFrete(peso, distancia);
                break;
            case 2:
                calculadora = new Frete(new CalculadoraFreteJadlog());
                resultado =calculadora.calcularFrete(peso, distancia);
                break;
            case 3:
                calculadora = new Frete(new CalculadoraFreteAzul());
                resultado = calculadora.calcularFrete(peso, distancia);
                break;
            default:
                System.out.println("Opcao invalida!");
                break;
        }
    
        System.out.printf("Resultados do Frete: %.2f ", resultado);
        
        sc.close();
    }
}
