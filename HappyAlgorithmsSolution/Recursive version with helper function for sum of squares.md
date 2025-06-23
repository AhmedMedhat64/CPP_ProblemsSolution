int sumOfSquares(int num) {
    int total = 0;
    while (num > 0) {
        int digit = num % 10;
        total += digit * digit;
        num /= 10;
    }
    return total;
}

std::string happyAlgorithmHelper(int num, std::vector<int>& IsSeen) {
    int numSum = sumOfSquares(num);

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
