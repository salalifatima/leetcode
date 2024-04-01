#88
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int m1 = m - 1;
        int n1 = n - 1;
        int nm = m + n - 1;

        while (m1 >= 0 && n1 >= 0) {
            if (nums1[m1] > nums2[n1]) {
                nums1[nm] = nums1[m1];
                m1--;
            } else {
                nums1[nm] = nums2[n1];
                n1--;
            }
            nm--;
        }
        while (n1 >= 0) {
            nums1[nm] = nums2[n1];
            n1--;
            nm--;
        }
    }
    int main() {
        int m;
        cin >> m;
        vector<int> nums1(m);
        for (int i = 0; i <= m; i++) {
            cin >> nums1[i];
        }
        int n;
        cin >> n;
        vector<int> nums2(n);
        for (int j = 0; j <= n; j++) {
            cin >> nums2[j];
        }
        merge(nums1, m, nums2, n);
        for (int num : nums1)
            cout << num << " ";
        cout << endl;
        return 0;
    }
};
