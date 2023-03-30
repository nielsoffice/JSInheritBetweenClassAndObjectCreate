# JSInheritBetweenClassAndObjectCreate
JavaScript Inherit between Class and Object.create

```JS
 // Inherit between Class and Object.create
    const PersonDev = {

      yearsOfExperience() {
        console.log( 'You are qualify '+ this.name + ' as you have '+ this.yExperience ); // suppose that I have property name yExperience
      },

      init(firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
      }

    }
    
    // Inherit from PersonDev Properties and method
    const nielWPDev = Object.create(PersonDev);

    // Inherit from PersonDev Properties and method
    const FreshDev = Object.create(PersonDev);

    // New Object FreshDev
    FreshDev.init = function(firstName, lastName, skills) {
      // Using method inside the function Object create
      // not New PersonDev(); instead  PersonDev.init.call();
      // skills additional property for FreshDev which obviously not exist to PersonDev
      PersonDev.init.call(this, firstName, lastName, this.skills = skills);
    }
    
    // Let's create object from FreshDev
    const em = Object.create(FreshDev);
    // Get Inherit method and properties
    em.init('emz', 'Leo', 'PHPDev')
```

```JS
 // Console.log | Result 
 > em
 // Result 
 {skills: 'PHPDev', firstName: 'emz', lastName: 'Leo'}
  firstName : "emz"
  lastName : "Leo"
  skills :  "PHPDev"
 [[Prototype]] : Object 
```
