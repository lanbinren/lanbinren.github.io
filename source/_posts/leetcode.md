---
title: leetcode 宝石与石头
---

771. 宝石与石头
给定字符串J 代表石头中宝石的类型，和字符串 S代表你拥有的石头。 S 中每个字符代表了一种你拥有的石头的类型，你想知道你拥有的石头中有多少是宝石。
J 中的字母不重复，J 和 S中的所有字符都是字母。字母区分大小写，因此"a"和"A"是不同类型的石头。
<!-- more -->
int numJewelsInStones(char* J, char* S) {
    int list['z'-'A'+1]={0},sum=0,i=0;
    while(S[i]!='\0'){
        list[S[i]-'A']++;
        i++;
    }
    i = 0;
    while(J[i]!='\0'){
        sum+=list[J[i]-'A'];
        i++;
    }
    return sum;
}

