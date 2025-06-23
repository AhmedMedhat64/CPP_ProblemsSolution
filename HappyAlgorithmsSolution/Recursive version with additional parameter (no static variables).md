std::string happyAlgorithmHelper(int num, std::vector<int>& IsSeen) {
    int temp = num, numSum = 0;
    while (temp > 0) {
        int digit = temp % 10;
        numSum += digit * digit;
        temp /= 10;
    }

    if (numSum == 1)
        return "Happy " + std::to_string(IsSeen.size() + 1);

    for (int val : IsSeen) {
        if (val == numSum)
            return "Sad " + std::to_string(IsSeen.size());
    }

    IsSeen.push_back(numSum);
    return happyAlgorithmHelper(numSum, IsSeen);
}

std::string happyAlgorithm(int num) {
    std::vector<int> IsSeen;
    return happyAlgorithmHelper(num, IsSeen);
}
