void happyAlgorithm(int num) {
    static std::vector<int> IsSeen;
    static bool firstCall = true;

    if (firstCall) {
        IsSeen.clear();
        firstCall = false;
    }

    int temp = num, numSum = 0;
    while (temp > 0) {
        int digit = temp % 10;
        numSum += digit * digit;
        temp /= 10;
    }

    if (numSum == 1) {
        std::cout << "Happy " << IsSeen.size() + 1 << "\n";
        firstCall = true;  // reset for next call
        return;
    }

    for (int val : IsSeen) {
        if (val == numSum) {
            std::cout << "Sad " << IsSeen.size() << "\n";
            firstCall = true;  // reset for next call
            return;
        }
    }

    IsSeen.push_back(numSum);
    happyAlgorithm(numSum);  // recursive call
}
