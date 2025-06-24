ReturnType function(ParamType param) {
    static StaticType staticVar;
    static bool firstCall = true;

    if (firstCall) {
        // Initialize/reset static variables here
        staticVar = /* initial value */;
        firstCall = false;
    }

    // Recursive logic here, possibly updating staticVar

    if (/* base case condition */) {
        firstCall = true;  // Reset flag for next fresh call
        return /* final result, possibly involving staticVar */;
    }

    // Update staticVar if needed
    // Recursive call with updated param
    return function(/* updated param */);
}
