
    void radixsort(vector<int>& r, int pos, int max){
    
        int digit = 1;

        while (max > 0){
            r = radix(r, l, pos, digit);
            digit *= 10;
            max /= 10;
        }

        return;
    }

    vector<int> radix(vector<int>& cur, int l, int pos, int digit){
        
        vector<vector<int>> sorted(10, vector<int>{});

        for (auto r : cur){
            sorted[r[pos] / digit % 10].push_back(r);
        }

        vector<int> res;
        for (int i = 0; i < 10; i ++){
            auto bucket = sorted[i];
            for (auto r : bucket){
                res.push_back(r);
            }
        }
        return res;
    }

