# ProjetPA
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        ContactManager manager = new ContactManager();
        Scanner scanner = new Scanner(System.in);
        int choix;

do {
            System.out.println("\n===== MENU CONTACTS =====");
            System.out.println("1. Afficher tous les contacts");
            System.out.println("2. Ajouter un contact");
            System.out.println("3. Supprimer un contact");
            System.out.println("4. Rechercher un contact");
            System.out.println("0. Quitter");
            System.out.print("Choix : ");
            choix = scanner.nextInt();
            scanner.nextLine(); // vider la ligne

  switch (choix) {
                case 1:
                    manager.afficherTous();
                    break;
                case 2:
                    System.out.print("Nom       : ");
                    String nom = scanner.nextLine();
                    System.out.print("Prénom    : ");
                    String prenom = scanner.nextLine();
                    System.out.print("Téléphone : ");
                    String tel = scanner.nextLine();
                    System.out.print("Email     : ");
                    String email = scanner.nextLine();
                    System.out.print("Catégorie : ");
                    String cat = scanner.nextLine();
                    System.out.print("Chemin photo (laisser vide si aucune) : ");
                    String photo = scanner.nextLine();
                    Contact c = new Contact(nom, prenom, tel, email, cat, photo);
                    manager.ajouter(c);
                    System.out.println("Contact ajouté.");
                    break;
                case 3:
                    System.out.print("Entrez le numéro du contact à supprimer : ");
                    int index = scanner.nextInt() - 1;
                    manager.supprimer(index);
                    break;
                case 4:
                    System.out.print("Mot-clé à rechercher : ");
                    String motCle = scanner.nextLine();
                    manager.rechercher(motCle);
                    break;
                case 0:
                    System.out.println("Au revoir !");
                    break;
                default:
                    System.out.println("Choix invalide.");
            }

  } while (choix != 0);
    }
}
