# OOP-in-C
My rules for OOP in C

```javascript
typedef struct _Base Base;
typedef struct _Subclass SubClass;
typedef void AbstractBase;
typedef void AbstractSubclass;

struct _Base{
  const char *name;
};

struct _SubClass{
  Base Base;           //first field is the Object it extends (its super class) it has the same name as the type.
  double extraField;
};


AbstractBase *Base_create       (unsigned int size);
AbstractBase *Subclass_create   (unsigned int size){ return Base_create(size==0 ? sizeof(Subclass) : size); }

const char *  Base_getName      (Base *base){ return base->name; }

bool Subclass_nameIsJohn (Subclass *subclass){
   //call function with "Subclass" as "Base"
   const char *myName = Base_getName(&subclass->Base);
   
   return strcmp(myName,"John")==0;
}

// Base *myBase = (Base *)mySubclassObject
// is the same as
// Base *myBase = &mySubclassObject->Base;


```
