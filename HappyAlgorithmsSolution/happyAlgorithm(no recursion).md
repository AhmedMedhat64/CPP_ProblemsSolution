std::string happyAlgorithm(int num) {
    std::vector<int> IsSeen;
    while (true) {
        std::vector<int> sepNum = calc_digits(num);
        int numSum = 0;
        for (auto i = 0; i < sepNum.size(); i++)
            numSum += sepNum[i] * sepNum[i];

        if (numSum == 1)
            return "Happy " + std::to_string(IsSeen.size() + 1);

        for (auto i = 0; i < IsSeen.size(); i++) {
            if (IsSeen[i] == numSum)
                return "Sad " + std::to_string(IsSeen.size() + i);
        }

        IsSeen.push_back(numSum);
        num = numSum;
    }
}
