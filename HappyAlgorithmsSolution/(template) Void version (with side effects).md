void function(ParamType param) {
    static StaticType staticVar;
    static bool firstCall = true;

    if (firstCall) {
        // Initialize/reset static variables here
        staticVar = /* initial value */;
        firstCall = false;
    }

    // Recursive logic here, possibly updating staticVar

    if (/* base case condition */) {
        // Output or perform side effect here (e.g., print, set globals)
        firstCall = true;  // Reset flag for next fresh call
        return;
    }

    // Update staticVar if needed
    // Recursive call with updated param
    function(/* updated param */);
}
