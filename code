import java.util.*;

class Person {
    protected String name;
    protected int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

class Patient extends Person {
    private int patientId;
    private String disease;

    public Patient(int patientId, String name, int age, String disease) {
        super(name, age);
        this.patientId = patientId;
        this.disease = disease;
    }

    public void displayPatient() {
        System.out.println("ID: " + patientId + ", Name: " + name + ", Disease: " + disease);
    }

    public int getPatientId() {
        return patientId;
    }
}

class Doctor extends Person {
    private String specialization;

    public Doctor(String name, int age, String specialization) {
        super(name, age);
        this.specialization = specialization;
    }

    public void displayDoctor() {
        System.out.println("Doctor: " + name + " - " + specialization);
    }
}

class Appointment {
    public Appointment(Patient p, Doctor d, String date) {
        System.out.println("Appointment booked on " + date);
        p.displayPatient();
        d.displayDoctor();
    }
}

class Billing {
    public Billing(Patient p, double amt) {
        System.out.println("Bill: ₹" + amt);
        p.displayPatient();
    }
}

public class HospitalManagementSystem {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        ArrayList<Patient> list = new ArrayList<>();
        Doctor d = new Doctor("Dr Kumar", 40, "Cardiology");

        while (true) {
            System.out.println("\n1.Add 2.View 3.Appointment 4.Bill 5.Exit");
            int ch = sc.nextInt();

            if (ch == 1) {
                System.out.print("ID: ");
                int id = sc.nextInt();
                sc.nextLine();
                System.out.print("Name: ");
                String name = sc.nextLine();
                System.out.print("Disease: ");
                String dis = sc.nextLine();

                list.add(new Patient(id, name, 20, dis));
            }

            else if (ch == 2) {
                for (Patient p : list) p.displayPatient();
            }

            else if (ch == 3) {
                System.out.print("Enter ID: ");
                int id = sc.nextInt();
                sc.nextLine();
                System.out.print("Date: ");
                String date = sc.nextLine();

                for (Patient p : list)
                    if (p.getPatientId() == id)
                        new Appointment(p, d, date);
            }

            else if (ch == 4) {
                System.out.print("Enter ID: ");
                int id = sc.nextInt();
                System.out.print("Amount: ");
                double amt = sc.nextDouble();

                for (Patient p : list)
                    if (p.getPatientId() == id)
                        new Billing(p, amt);
            }

            else if (ch == 5) {
                break;
            }
        }
    }
}
