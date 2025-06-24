std::string happyAlgorithm(int num) {
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
        firstCall = true;  // reset for next call
        return "Happy " + std::to_string(IsSeen.size() + 1);
    }

    for (int val : IsSeen) {
        if (val == numSum) {
            firstCall = true;
            return "Sad " + std::to_string(IsSeen.size());
        }
    }

    IsSeen.push_back(numSum);
    return happyAlgorithm(numSum);
}
