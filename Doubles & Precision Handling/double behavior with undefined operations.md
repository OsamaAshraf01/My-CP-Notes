#doubles
In C++, `double` and `long double` types behaves differently with undefined and unrepresentable operations (e.g. division by zero, sqrt of negative, logarithm of non-positive, or any operation between two or more undefined operations). Instead of causing a Runtime Error, they produce values like `nan`, `inf`, `-inf`, `-0.0`.

To check double expression, you can use `std::isinf` and `std::isnan`.