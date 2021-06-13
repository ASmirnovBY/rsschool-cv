# Junior RS CV

1. Alexander Smirnov
2. BY Minsk, email: alex.smirnou94@gmail.com
3. I want to be a good mobile programmer. I'll learn languages like java and Kotlin. My goals are to be a software architect and good human :)
4. My skills: Electronic, microelectronic, Java, git, SQL, Kotlin(learning)
5. Codes examples:
```Java
    public class PatientServicesImpl implements PatientService {

    @Override
    public void addNewPatient(Patient patient) throws ServiceException {
        DAOFactory daoFactory = DAOFactory.getInstance();
        PatientDao patientDaoImpl = daoFactory.getPatientDao();
        try {
            patientDaoImpl.insert(patient);
        } catch (DAOException e) {
            throw new ServiceException("", e);
        }
    }

    @Override
    public List<Patient> allPatients() throws ServiceException {
        DAOFactory daoFactory = DAOFactory.getInstance();
        PatientDao patientDaoImpl = daoFactory.getPatientDao();
        List<Patient> patients;
        try {
            patients = patientDaoImpl.findAll();
        } catch (DAOException e) {
            throw new ServiceException("", e);
        }
        return patients;
    }

    @Override
    public List<Patient> findByDiagnosis(String diagnosis) throws ServiceException {
        DAOFactory daoFactory = DAOFactory.getInstance();
        PatientDao patientDaoImpl = daoFactory.getPatientDao();
        List<Patient> patientWithDiagnosis;

        try {
            patientWithDiagnosis = patientDaoImpl.findAll()
                    .stream()
                    .filter(
                            patient -> patient.getDiagnosis().equalsIgnoreCase(diagnosis)
                    ).collect(Collectors.toList());
        } catch (DAOException e) {
            throw new ServiceException(e);
        }

        return patientWithDiagnosis;
    }

    @Override
    public List<Patient> findByCartNumber(int cartNumber) throws ServiceException {
        DAOFactory daoFactory = DAOFactory.getInstance();
        PatientDao patientDaoImpl = daoFactory.getPatientDao();
        List<Patient> patientCartNumberInRange;
        try {
            patientCartNumberInRange = patientDaoImpl.findAll()
                    .stream()
                    .filter(patient -> patient.getCartNumber() == cartNumber)
                    .collect(Collectors.toList());
        } catch (DAOException e) {
            throw new ServiceException(e);
        }
        return patientCartNumberInRange;
    }

    @Override
    public List<Patient> findByPhoneNumber(String phone) throws ServiceException {
        DAOFactory daoFactory = DAOFactory.getInstance();
        PatientDao patientDaoImpl = daoFactory.getPatientDao();
        List<Patient> patientFindPhone;
        try {
            patientFindPhone = patientDaoImpl.findAll().stream()
                    .filter(
                            patient -> patient.getNumber().contains(phone)
                            )
                    .collect(Collectors.toList());
        } catch (DAOException e) {
            throw new ServiceException(e);
        }
        return patientFindPhone;
    }
}
```
6. See my expiriense in https://github.com/ASmirnovBY/JavaTraining
7. Belarusian State University of Informatics and Radioelectronics 2016, Java WEB (Epam training not finished)
8. English A2
