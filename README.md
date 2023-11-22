void grade10(const char* path) {
    ifstream file (path);
    string s;
    getline (file, s);
    while (!file.eof()) {
        int count=0;
        string name="";
        getline (file, s);
        for (int i=0; i<(int)s.size(); i++) {
            if(s[i]==',') {
                count++;
            }
            if (count==1 && s[i]!=',' ) name+=s[i];
            else if (count==2 && s[i-1]==',') name= name + " " +s[i];
            else if (count==2 && s[i]!=',') name+=s[i]; 
            else if (count==5 && s[i]=='1'&& s[i+1]=='0') cout << name << endl;
        }
        
    }
}
