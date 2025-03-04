# LLVM

## Генерация LLVM IR с определенными инструкциями

### trunc

```C++
char convertToChar(int num) {
    return num;
}
```

`-S -emit-llvm`

### getelemptr

```C++
struct SomeData {
    int some_int;
    double some_double;
};

int *getIntPtr(SomeData *data) {
    return &(data->some_int);
}
```

`-S -emit-llvm`

### srem

```C++
int getReminderOfDivision(int a, int b) {
    return a % b;
}
```

`-S -emit-llvm`

### lshr

```C++
int shiftNumberRight(unsigned int num) {
    return num >> 1;
}
```

`-S -emit-llvm`

### zext

```C++
#include <cstdint>

uint64_t extendNumber(uint32_t num) {
    return num;
}
```

`-S -emit-llvm`

### bitcast

```C++
float bitCastToFloat(int num) {
    return *reinterpret_cast<float *>(&num);
}
```

`-S -emit-llvm -O1`

### sitofp

```C++
float staticCastToFloat(int num) {
    return static_cast<float>(num);
}
```

### select

```C++
int conditionalChoice(bool pred, int a, int b) {
    return pred ? a : b;
}
```

`-S -emit-llvm -O1`

### fpext

```C++
double extendToDouble(float num) {
    return static_cast<double>(num);
}
```

`-S -emit-llvm`


### tail call

```C++
int factorial(int num) {
    if (num <= 1) {
        return 1;
    }
    return num * factorial(num - 1);
}

int sumOfFactorials(int a, int b) {
    return factorial(a) + factorial(b);
}
```

`-S -emit-llvm -O1`
