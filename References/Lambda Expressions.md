#references
- Pass variable by value/reference:
    ```C++
    vector<int> v = {1, 2, 3, 4};
    int val = 10;

    // [] capture clause

    // 1. pass outer variables as CONST VALUE
    auto add_val = [val](vector<int> &v){
        for(int& item : v)
            item += val;

        // val++ -> Error
    }
    add_val(v); // add 10 tp each element in v
    ```

    ```C++
    // 2. pass outer variables by VALUE
    auto add_val = [val](vector<int> &v) mutable{
        val += 5;
        for(int& item : v)
            item += val;
    }
    add_val(v); // add 15 to each element in v
    cout << val; // 10
    ```

    ```C++
    // 3. pass outer variables by REFERENCE
    auto add_val = [&val](vector<int> &v) {
        val += 5;
        for(int& item : v)
            item += val;
    }
    add_val(v); // add 15 to each element in v
    cout << val; // 15

    ```


- Passing all variables by value/reference:
    ```C++
    // To pass all variables by VALUE
    auto add_val = [=](vector<int> &v) {
        val += 5;
        for(int& item : v)
            item += val;
    }
    ```

    ```C++
    // To pass all variables by REFERENCE
    auto add_val = [&](vector<int> &v) {
        val += 5;
        for(int& item : v)
            item += val;
    }
    ```

    ```C++
    [=, &b] // means all variables will be passed by value except for b, it will be passed by reference
    [&, b] // means all variables will be passed by reference except for b, it will be passed by value
    ```

- **NOTE:** Static variables are visible inside the lambda function
