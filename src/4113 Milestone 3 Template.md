# IY4113 Milestone 3

| Assessment Details | Please Complete All Details  |
| ------------------ | ---------------------------- |
| Group              | B                            |
| Module Title       | Applied Software Engineering |
| Assessment Type    | ASSESSMENT 1: Milestone 3    |
| Module Tutor Name  | Jonathan shore               |
| Student ID Number  | P505853                      |
| Date of Submission | 17 May 2026                  |
| Word Count         |                              |

- [ ] *I confirm that this assignment is my own work. Where I have referred to academic sources, I have provided in-text citations and included the sources in
  the final reference list.*

- [ ] *Where I have used AI, I have cited and referenced appropriately.

------------------------------------------------------------------------------------------------------------------------------

### Research (minimum of 2, at least 3)

---

Conduct research to support your coding process, including use of code examples, tutortials, documentation and AI tools (if used).

Use the structure below to capture your evidence:

------------------------------------------------------------------------------------------------------------------------------

Title of research: Java Classes and Objects / Class Attributes

Reference (link): https://www.w3schools.com/java/java_class_attributes.asp

How does the research help with coding practise?:
This research helped me understand how Java classes store data using attributes. It also helped me understand that each object created from a class can have its own values. This is useful for my program because a student, a course,

Key coding ideas you could reuse in your program:

- Use class attributes to store object information.
- Keep related data inside one class.
- Create different objects from the same class.
- Use clear variable names so the purpose of each attribute is easy to understand.

Screenshot of research:
![Screenshot 2026-05-17 at 19.35.44.jpg](../../IdeaProjects/4113/src/Screenshot%202026-05-17%20at%2019.35.44.jpg)

------------------------------------------------------------------------------------------------------------------------------

Title of research: Java Encapsulation, Getters and Setters

Reference (link):https://www.w3schools.com/java/java_encapsulation.asp

How does the research help with coding practise?:
This research helped me understand encapsulation. Encapsulation means that class attributes should usually be private and accessed through public getter and setter methods. This improves the structure of the code because it controls how data is read and changed.

Key coding ideas you could reuse in your program:

- Make attributes private.
- Use getter methods to return attribute values.
- Use setter methods to update attribute values safely.
- Keep code organised into clear sections such as attributes, constructors, getters, setters, and other methods.

Screenshot of research:
![Screenshot 2026-05-17 at 19.39.14.jpg](../../IdeaProjects/4113/src/Screenshot%202026-05-17%20at%2019.39.14.jpg)

------------------------------------------------------------------------------------------------------------------------------

**Title of research:** Java Constructors

**Reference (link):** https://www.baeldung.com/java-constructors

**How does the research help with coding practise?:**  
This research helped me understand how constructors are used to set up an object when it is first created. Constructors are useful because they allow important values to be assigned immediately, instead of leaving an object empty or incomplete.

**Key coding ideas you could reuse in your program:**

- Use constructors to initialise objects.
- Pass important data into the constructor as parameters.
- Use the `this` keyword to refer to the current object's attributes.
- Keep constructor code simple and focused on setting initial values.

**Screenshot of research:**  
![Screenshot 2026-05-17 at 19.44.46.jpg](../../IdeaProjects/4113/src/Screenshot%202026-05-17%20at%2019.44.46.jpg)

------------------------------------------------------------------------------------------------------------------------------

### Program Code

---

Paste the current program code created so far. It does not have to be runnable code (document though if it does not work!)

------------------------------------------------------------------------------------------------------------------------------

*Program code goes here:*
Journey class

```java
// This class stores one public transport journey for CityRide Lite.
import java.math.BigDecimal;


public class Journey {

    // Attributes
    private int journeyId;
    private String journeyDate;
    private int fromZone;
    private int toZone;
    private CityRideDataset.TimeBand timeBand;
    private CityRideDataset.PassengerType passengerType;
    private int zonesCrossed;
    private BigDecimal baseFare;
    private BigDecimal discountAmount;
    private BigDecimal discountedFare;
    private BigDecimal chargedFare;

    // Constructors
    public Journey() {
        this.journeyId = 0;
        this.journeyDate = "";
        this.fromZone = 1;
        this.toZone = 1;
        this.timeBand = CityRideDataset.TimeBand.OFF_PEAK;
        this.passengerType = CityRideDataset.PassengerType.ADULT;
        this.zonesCrossed = 1;
        this.baseFare = BigDecimal.ZERO;
        this.discountAmount = BigDecimal.ZERO;
        this.discountedFare = BigDecimal.ZERO;
        this.chargedFare = BigDecimal.ZERO;
    }

    public Journey(int journeyId, String journeyDate, int fromZone, int toZone,
                   CityRideDataset.TimeBand timeBand,
                   CityRideDataset.PassengerType passengerType) {
        this.journeyId = journeyId;
        this.journeyDate = journeyDate;
        this.fromZone = fromZone;
        this.toZone = toZone;
        this.timeBand = timeBand;
        this.passengerType = passengerType;
        this.zonesCrossed = calculateZonesCrossed();
        this.baseFare = BigDecimal.ZERO;
        this.discountAmount = BigDecimal.ZERO;
        this.discountedFare = BigDecimal.ZERO;
        this.chargedFare = BigDecimal.ZERO;
    }

    // Getter methods
    public int getJourneyId() {
        return journeyId;
    }

    public String getJourneyDate() {
        return journeyDate;
    }

    public int getFromZone() {
        return fromZone;
    }

    public int getToZone() {
        return toZone;
    }

    public CityRideDataset.TimeBand getTimeBand() {
        return timeBand;
    }

    public CityRideDataset.PassengerType getPassengerType() {
        return passengerType;
    }

    public int getZonesCrossed() {
        return zonesCrossed;
    }

    public BigDecimal getBaseFare() {
        return baseFare;
    }

    public BigDecimal getDiscountAmount() {
        return discountAmount;
    }

    public BigDecimal getDiscountedFare() {
        return discountedFare;
    }

    public BigDecimal getChargedFare() {
        return chargedFare;
    }

    // Setter methods
    public void setJourneyId(int journeyId) {
        this.journeyId = journeyId;
    }

    public void setJourneyDate(String journeyDate) {
        this.journeyDate = journeyDate;
    }

    public void setFromZone(int fromZone) {
        this.fromZone = fromZone;
        this.zonesCrossed = calculateZonesCrossed();
    }

    public void setToZone(int toZone) {
        this.toZone = toZone;
        this.zonesCrossed = calculateZonesCrossed();
    }

    public void setTimeBand(CityRideDataset.TimeBand timeBand) {
        this.timeBand = timeBand;
    }

    public void setPassengerType(CityRideDataset.PassengerType passengerType) {
        this.passengerType = passengerType;
    }

    public void setBaseFare(BigDecimal baseFare) {
        this.baseFare = baseFare;
    }

    public void setDiscountAmount(BigDecimal discountAmount) {
        this.discountAmount = discountAmount;
    }

    public void setDiscountedFare(BigDecimal discountedFare) {
        this.discountedFare = discountedFare;
    }

    public void setChargedFare(BigDecimal chargedFare) {
        this.chargedFare = chargedFare;
    }

    // Calculation methods
    public int calculateZonesCrossed() {
        return Math.abs(toZone - fromZone) + 1;
    }
}
```

Fare Calculator

```java
// This class calculates fares, discounts, and daily cap charges.
import java.math.BigDecimal;
import java.math.RoundingMode;
// This class calculates fares, discounts, and daily cap charges.
public class FareCalculator {

    // Attributes
    private BigDecimal adultRunningTotal;
    private BigDecimal studentRunningTotal;
    private BigDecimal childRunningTotal;
    private BigDecimal seniorRunningTotal;

    // Constructors
    public FareCalculator() {
        this.adultRunningTotal = BigDecimal.ZERO;
        this.studentRunningTotal = BigDecimal.ZERO;
        this.childRunningTotal = BigDecimal.ZERO;
        this.seniorRunningTotal = BigDecimal.ZERO;
    }

    // Getter methods
    public BigDecimal getAdultRunningTotal() {
        return adultRunningTotal;
    }

    public BigDecimal getStudentRunningTotal() {
        return studentRunningTotal;
    }

    public BigDecimal getChildRunningTotal() {
        return childRunningTotal;
    }

    public BigDecimal getSeniorRunningTotal() {
        return seniorRunningTotal;
    }

    // Setter methods
    public void setAdultRunningTotal(BigDecimal adultRunningTotal) {
        this.adultRunningTotal = adultRunningTotal;
    }

    public void setStudentRunningTotal(BigDecimal studentRunningTotal) {
        this.studentRunningTotal = studentRunningTotal;
    }

    public void setChildRunningTotal(BigDecimal childRunningTotal) {
        this.childRunningTotal = childRunningTotal;
    }

    public void setSeniorRunningTotal(BigDecimal seniorRunningTotal) {
        this.seniorRunningTotal = seniorRunningTotal;
    }

    // Fare methods
    public BigDecimal calculateBaseFare(int fromZone, int toZone, CityRideDataset.TimeBand timeBand) {
        BigDecimal baseFare = CityRideDataset.getBaseFare(fromZone, toZone, timeBand);

        if (baseFare == null) {
            return BigDecimal.ZERO.setScale(2, RoundingMode.HALF_UP);
        }

        return roundToTwoDecimals(baseFare);
    }

    public BigDecimal getDiscountRate(CityRideDataset.PassengerType passengerType) {
        BigDecimal discountRate = CityRideDataset.DISCOUNT_RATE.get(passengerType);

        if (discountRate == null) {
            return BigDecimal.ZERO;
        }

        return discountRate;
    }

    public BigDecimal getDailyCap(CityRideDataset.PassengerType passengerType) {
        BigDecimal dailyCap = CityRideDataset.DAILY_CAP.get(passengerType);

        if (dailyCap == null) {
            return BigDecimal.ZERO.setScale(2, RoundingMode.HALF_UP);
        }

        return roundToTwoDecimals(dailyCap);
    }

    public BigDecimal getRunningTotal(CityRideDataset.PassengerType passengerType) {
        if (passengerType == CityRideDataset.PassengerType.STUDENT) {
            return studentRunningTotal;
        } else if (passengerType == CityRideDataset.PassengerType.CHILD) {
            return childRunningTotal;
        } else if (passengerType == CityRideDataset.PassengerType.SENIOR_CITIZEN) {
            return seniorRunningTotal;
        }

        return adultRunningTotal;
    }

    public void updateRunningTotal(CityRideDataset.PassengerType passengerType, BigDecimal chargedFare) {
        if (passengerType == CityRideDataset.PassengerType.STUDENT) {
            studentRunningTotal = studentRunningTotal.add(chargedFare);
        } else if (passengerType == CityRideDataset.PassengerType.CHILD) {
            childRunningTotal = childRunningTotal.add(chargedFare);
        } else if (passengerType == CityRideDataset.PassengerType.SENIOR_CITIZEN) {
            seniorRunningTotal = seniorRunningTotal.add(chargedFare);
        } else {
            adultRunningTotal = adultRunningTotal.add(chargedFare);
        }
    }

    public void applyFareToJourney(Journey journey) {
        BigDecimal baseFare = calculateBaseFare(
                journey.getFromZone(),
                journey.getToZone(),
                journey.getTimeBand()
        );

        BigDecimal discountRate = getDiscountRate(journey.getPassengerType());
        BigDecimal discountAmount = baseFare.multiply(discountRate);
        BigDecimal discountedFare = baseFare.subtract(discountAmount);
        BigDecimal chargedFare = applyDailyCap(journey.getPassengerType(), discountedFare);

        journey.setBaseFare(roundToTwoDecimals(baseFare));
        journey.setDiscountAmount(roundToTwoDecimals(discountAmount));
        journey.setDiscountedFare(roundToTwoDecimals(discountedFare));
        journey.setChargedFare(roundToTwoDecimals(chargedFare));

        updateRunningTotal(journey.getPassengerType(), roundToTwoDecimals(chargedFare));
    }

    public BigDecimal applyDailyCap(CityRideDataset.PassengerType passengerType, BigDecimal discountedFare) {
        BigDecimal runningTotal = getRunningTotal(passengerType);
        BigDecimal dailyCap = getDailyCap(passengerType);

        if (runningTotal.compareTo(dailyCap) >= 0) {
            return BigDecimal.ZERO.setScale(2, RoundingMode.HALF_UP);
        }

        if (runningTotal.add(discountedFare).compareTo(dailyCap) > 0) {
            return dailyCap.subtract(runningTotal);
        }

        return discountedFare;
    }

    public BigDecimal roundToTwoDecimals(BigDecimal value) {
        return value.setScale(2, RoundingMode.HALF_UP);
    }

    public void resetTotals() {
        adultRunningTotal = BigDecimal.ZERO;
        studentRunningTotal = BigDecimal.ZERO;
        childRunningTotal = BigDecimal.ZERO;
        seniorRunningTotal = BigDecimal.ZERO;
    }
}
```

------------------------------------------------------------------------------------------------------------------------------

### Updated Gantt Chart

------------------------------------------------------------------------------------------------------------------------------

![Screenshot 2026-05-17 at 20.13.00.jpg](../../IdeaProjects/4113/src/Screenshot%202026-05-17%20at%2020.13.00.jpg)

------------------------------------------------------------------------------------------------------------------------------

### Diary Entries

------------------------------------------------------------------------------------------------------------------------------
#### Diary Entry 1
I researched Java classes, attributes, encapsulation, getters, setters, and constructors. This helped me understand how to organize my programs using object-oriented programming. I used this research to create clearer classes with private attributes and public getter and setter methods.

#### Diary Entry 2
I created a Journey class to store information about a journey, such as the Journey ID, date, zone, passenger type, time range, and fare details. I used a constructor to create a journey object and added getter and setter methods to securely access and update the data. I also added a method to calculate of zones traveled.

#### Diary Entry 3
I created a FareCalculator class to calculate the base fare, discount, discounted fare, applicable fare, and daily limit. I used BigDecimal because it's more accurate for monetary values. This class separates the fare calculation from the trip data, making the code more organized.



------------------------------------------------------------------------------------------------------------------------------
