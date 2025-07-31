# -Programa-o-Orientada-a-Objetos-POO-
// Superclasse
class Animal {
    String nome;
    int idade;

    // Construtor da superclasse
    public Animal(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    public void emitirSom() {
        System.out.println("O animal faz um som.");
    }
}

// Subclasse
class Cachorro extends Animal {
    String raca;

    // Construtor da subclasse
    public Cachorro(String nome, int idade, String raca) {
        super(nome, idade); // Chama o construtor da superclasse
        this.raca = raca;
    }

    @Override
    public void emitirSom() {
        System.out.println("O cachorro late: Au au!");
    }

    public void abanarRabo() {
        System.out.println(nome + " está abanando o rabo.");
    }
}

// Classe Main
public class Main {
    public static void main(String[] args) {
        // Objeto da Superclasse
        Animal meuAnimal = new Animal("Leão", 5);
        System.out.println("Nome do animal: " + meuAnimal.nome + ", Idade: " + meuAnimal.idade);
        meuAnimal.emitirSom();

        System.out.println("---");

        // Objeto da Subclasse
        Cachorro meuCachorro = new Cachorro("Rex", 3, "Golden Retriever");
        System.out.println("Nome do cachorro: " + meuCachorro.nome + ", Idade: " + meuCachorro.idade + ", Raça: " + meuCachorro.raca);
        meuCachorro.emitirSom();
        meuCachorro.abanarRabo();

        System.out.println("---");

        // Polimorfismo
        Animal outroCachorro = new Cachorro("Buddy", 7, "Poodle");
        System.out.println("Nome do outro cachorro: " + outroCachorro.nome + ", Idade: " + outroCachorro.idade);
        outroCachorro.emitirSom();
    }
}
