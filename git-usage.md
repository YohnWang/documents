# ����
## ȫ������
git config --global user.name "Your Name"
git config --global user.email "email@example.com"

//����ȫ�ֵ��û�������Ϣ���û������û� ����

## �ֲ�����
git config --local user.name "Your Name" 
git config --local user.email "email@example.com"

//--local ���������ʡ�� Ч����ͬ

//���嵱ǰ�ֿ������ύʹ�õ���������������

## ��ʼ��
git init //����ǰĿ¼������һ��git�ֿ�
git init <dir-name> //ָ��Ŀ¼������git�ֿ� ���� git init test-dir



## ��ɾ�ļ�

git add --all //�������޸���ӵ��ݴ���
git add file.txt //��ָ���ļ���ӵ��ݴ���

git rm test.txt //ɾ���ļ� 

git rm --cached test.txt //�Ӱ汾�������Ƴ��ļ� -n���Ա�ʾ��Ϸ

git checkout -- test.txt //���˵�����ύ�����

git checkout <commit> <file> //���ļ�����Ϊָ��commit�����ݣ�����ӵ��ݴ���

git checkout <commit> //���˵�ָ����commit

git commit -m "description"

## Զ�ֿ̲�

git remote 
git remote -v	//�鿴����Զ�̿�
git remote add origin https://github.com/xxxxxx/xxxxx //����һ��Զ�̿� originΪԶ�̿�����
git remote rm name
git remote rename name_before name_after

git push -u origin master   //���ط�֧�ĸ���,���͵�Զ������ -u��������Ĭ�ϵ��������� �����´ο���ֱ��ʹ��git push������Ĭ�ϵ�Զ������ masterΪ��֧��

git fetch origin <master>   //��ȡԶ�̸��� fetch֮�󲻻�ֱ���޸ı������� ��Ҫ�ϲ� ��ִ��git merge origin/master

## �ֿ�״̬

git status 

git diff file.txt

git log  //��ʾ���������Զ���ύ��־

git log -n <number> //��ʾnumber���ύ��־

git log --oneline //ÿ���ύ��־ֻ��ʾһ��

git log --stat //��ʾ��ϸ��Ϣ

git ls-files //�г�����汾���Ƶ��ļ�

## ��¡Զ�ֿ̲�
git clone <repo> //��ָ����Զ�ֿ̲��¡����ǰĿ¼
git clone <repo> <dir> //��ָ����Զ�ֿ̲��¡��ָ��Ŀ¼

## ��֧

git branch name //������Ϊname�ķ�֧

git checkout name //�л�����Ϊname�ķ�֧

git merge name //�ϲ�ָ������Ϊname�ķ�֧����ǰ��֧ git merge origin/master ->Զ��

git branch -d name //ɾ����֧

git branch -r //�鿴Զ�̷�֧

git branch -a //�г����з�֧



## �ع�

git revert <commit> //�ָ���ָ����commit��֧��ע����Ȼ������һ�ε�commit

git reset //TODO

git submodule add https://github.com/xxxxxx/xxxxx //���һ����ģ�� ֮����add .gitmodules����ģ���Ŀ¼ 

git submodule init //cloneһ������ģ�����Ŀʱ ��һ����Ҫִ�� ֮����Ҫ

git submodule update //������ģ��