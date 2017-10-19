##Vagrant....##

1. Vagrant 넌 뭐하는놈이냐?
	- 사용하기 간편한 Virtual Machine 
	- VM의 생성과 시작 그리고 삭제를 편리하게 해주는 툴
	- Virtualbox, VMware등이 있어야 사용가능
	
2. 장점?
	- 과거 구축했던 개발 및 운영 환경을 즉시 재현할 수 있다.
	- 개발자가 만든 VM 이미지를 다른 개발자들과 공유할 수 있다.
	- VM 구성 및 배포를 커맨드 몇 번만으로 빠르게 진행할 수 있다.
	- 개발자가 구성한 VM을 서버에서도 그대로 사용할 수 있다.
	- VM 공유 기능을 제공한다.
	- 설치가 매우 쉽다.
	- 소프트웨어 구성 비용이 없다.
	- 유지보수 비용을 최소화할 수 있다.
	
3. 단점?
	- 오픈스택과 같은 Cloud IaaS를 구성하지 않는다.
	- Network, Storage, Compute 가상화를 포함하는 가상화 기술을 제공하지는 않는다.
	- 그럴싸한 Web UI 제공하지 않는다.
	- VMware를 기반으로 사용하기 위해서는 유료 플러그인을 구매해야한다.

4. Docker와의 차이점
	
	|Vagrant|Docker|
	|:---:|:---:|
	| 하이퍼바이저형|컨테이너형|
	
	- Vagrant : OS가상화로 호스트 운영체제와 거의 완벽한 독립적 환경 
	- Docker : OS가상화를 하지 않고 호스트의 커널을 공유  
	 
5. Virtualbox 설치
	- https://www.virtualbox.org/wiki/Downloads

6. Vagrant 설치
	- https://www.vagrantup.com/downloads.html 에서 맞는버전 다운로드 
	
7. centos7 설치
	- ```vagrant init centos/7```
	- (https://app.vagrantup.com/boxes/search 에가면 다른 이미지도 있어요)
	 
8. Vagrant 실행
	- ```vagrant up```
	
9. VM ssh 접속
	- ```vagrant ssh```
	
10. Host와의 공유폴더 설정
	- ```vi Vagrantfile```
	- ```config.vm.synced_folder "host 절대경로 또는 프로젝트 루트 기준 상대경로", "vm내 절대경로"``` 추가
	- 근데... 실시간 공유가 안됨.... ```vagrant reload```를 해줘야함.
	
11. 내보내기
	- ```vagrant package```
	- 옵션 설명 : https://www.vagrantup.com/docs/cli/package.html
	
12. 불러오기
	- ```vagrant box add new_box package.box``` > BOX를 new_box라는 이름으로 추가
	- ```vagrant init new_box``` > new_box로 설정파일 만들기
	- ```vagrant up```
	- 이미 프로젝트에 Vagrantfile이 공유되 있다면 box추가 후 vagrant up을 하면 됨.

13. VM 제거
	- ```vagrant destroy```
	
	
출처 

 - https://www.vagrantup.com
 - http://temp123.tistory.com/31
 - https://medium.com/@darkrasid/docker%EC%99%80-vm-d95d60e56fdd
 - http://manseok.blogspot.kr/2014/09/vagrant.html
 - https://oddpoet.net/blog/2014/04/11/share-vagrant-box/
