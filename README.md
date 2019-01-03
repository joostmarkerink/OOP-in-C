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
  Base Base;
  double value;
};


AbstractBase *Base_create       (unsigned int size);
AbstractBase *Subclass_create   (unsigned int size){ return Base_create(size==0 ? sizeof(Subclass) : size); }

const char *  Base_getName      (AbstractBase *base){ return ((Base *)base)->name; }
double        Subclass_getValue (AbstractSubclass *subclass){ return ((Subclass *)subclass)->value; }

```
