AI researcher 
White Hacker  
love meditation and intellectual catharsis 
GOD level in Tryhackme 

![01](https://github.com/hero-rq/hero-rq/assets/80503808/201c0a8e-ba59-4deb-9b5d-bdffb84fc405)
![02](https://github.com/hero-rq/hero-rq/assets/80503808/fc76c6ca-8aac-4237-b4eb-91eec8d78b7c)

GOD level in Tryhackme  (from 13/09/2022 subscribed) - It took few months


#Publishing

Cryptocurrency Investment Strategy Through Blockchain Understanding (April 2022)
Cho, Y., Blockchain, Cryptocurrency, Bookk publisher    
● Topics: Blockchain and Cryptocurrency
● [isbn] : 9791137281592  paper book
● [isbn] : 9791137281356  electronic book


Basic Lectures for White Hackers (May 2022)  
Cho, Y., Hacking, Exploit, Bookk publisher    
● Topics: Web hacking and Reverse engineering 
● [isbn] : 9791137283008  


Advanced Lectures for White Hackers (Jun 2022)
Cho, Y., Cybersecurity in Metaverse. Bookk publisher
● Topics: Cybersecurity in Metaverse
● Programming Languages, Various attacks
● [isbn] : 9791137283855


블록체인 기반 언어 학습 토큰 생태계는 한국어 학습자와 원어민 교사를 연결하는 플랫폼을 제공합니다. 이 플랫폼은 블록체인 기술과 분산형 애플리케이션(DApp)을 활용하여 사용자의 편의성을 최대화하고, 교사와 학생 사이의 매칭, 예약, 지불 등의 프로세스를 투명하게 관리합니다.

(참가자: 이 생태계에는 세 가지 주요 참가자가 있습니다: 이용자(한국어 학습자), 선생님(한국어 원어민 교사), 그리고 중개자(플랫폼 운영자))

이용자: 이용자는 플랫폼에서 토큰을 구매하여 교사와 수업을 예약하고, 수업 후에는 피드백을 제공하여 교사의 수업을 평가합니다.

선생님: 선생님은 이용자에게 한국어를 가르칩니다. 수업이 완료되면, 교사는 토큰을 통해 보상을 받습니다. 교사는 또한 피드백을 받아 자신의 교육 방법을 개선하고, 학생에게 더 나은 학습 경험을 제공할 수 있습니다.

중개자: 중개자는 이용자와 선생님 사이를 연결하고, 지불 및 보상 프로세스를 관리합니다. 추가적으로, 언어 능력 테스트, 일정 관리, 고객 지원 등의 서비스를 제공할 수 있습니다.

매칭 알고리즘: 사용자의 학습 목표, 언어 수준, 수업 빈도 등의 조건을 고려하여 최적의 교사를 매칭합니다. 이 알고리즘은 DApp 내에서 실행되어, 사용자와 교사 사이의 매칭을 자동화합니다.

학습 자료: 기본적인 언어 학습 자료 뿐만 아니라, 교사가 직접 만든 고유의 학습 자료를 활용할 수 있습니다. 이런 방식은 교사와 학생이 수업에서 사용할 주제를 선택하고, 그 주제에 대해 깊이 있게 토론하거나 작문하는 기회를 제공합니다. 이는 학습자의 언어 학습을 더욱 효과적으로 만듭니다.

블록체인 기반 언어 학습 토큰 생태계는 이용자, 선생님, 중개자가 함께 작동하며, 블록체인 기술과 스마트 계약을 활용하여 투명하고 안전한 언어 학습 환경을 제공합니다. 이는 한국어 학습을 더욱 쉽고 편리하게 만들어, 효과적인 언어 학습 경험을 제공합니다. 제가 생각하기에 이것의 가장 큰 이점 중 하나는 이러한 방식 자체를 다른 언어에도 확장하여 국제적인 관점에서 서로 언어를 익히는 것을 도와주는 블록체인을 만들 수 있다는 것입니다. 

(아래의 코드는 모두 위의 내용을 구현할 수 있는 간략한 코드 예시입니다.)   


스마트 컨트랙트

토큰 관리: 이용자가 토큰을 구매하고, 선생님에게 지불할 수 있도록 토큰을 발행하고 관리하는 스마트 컨트랙트가 필요합니다. 이 스마트 컨트랙트는 토큰의 발행, 전송, 밸런스 조회 등의 기능을 제공합니다.
수업 예약 및 보상: 이용자가 선생님을 선택하고 수업을 예약할 수 있도록 하는 스마트 컨트랙트도 필요합니다. 수업이 정상적으로 완료된 후에는 토큰이 선생님의 계정으로 전송되도록 합니다.
보험금 관리: 선생님의 악의적인 행동에 대비하여 보험금을 관리하는 스마트 컨트랙트를 구현합니다. 선생님은 수업 전에 보험금을 제시하고, 수업이 정상적으로 완료되면 보험금이 반환되도록 합니다.
거버넌스: 이용자가 수업이 정상적으로 완료되지 않았다고 주장할 경우, 블록체인 거버넌스에 의해 문제를 해결합니다. 투표 기능을 포함하는 거버넌스 스마트 컨트랙트를 구현합니다.

pragma solidity ^0.5.0;

contract LanguageLearningToken {
    string  public name = "LanguageLearningToken";
    string  public symbol = "LLT";
    uint256 public totalSupply = 1000000000000000000000000; // 1 million tokens
    uint8   public decimals = 18;

    event Transfer(
        address indexed _from,
        address indexed _to,
        uint256 _value
    );

    event Approval(
        address indexed _owner,
        address indexed _spender,
        uint256 _value
    );

    mapping(address => uint256) public balanceOf;
    mapping(address => mapping(address => uint256)) public allowance;

    // Define a structure to represent a class
    struct Class {
        address student;
        address teacher;
        uint256 tokenAmount;
        uint256 insuranceAmount; // New field for insurance
        bool completed;
    }

    // Mapping from class ID to Class struct
    mapping(uint256 => Class) public classes;

    // Counter to generate unique class ID
    uint256 public nextClassId = 0;

    constructor() public {
        balanceOf[msg.sender] = totalSupply;
    }

    // More functions...

    function createClass(address _teacher, uint256 _tokenAmount, uint256 _insuranceAmount) public returns (uint256) {
        uint256 newClassId = nextClassId++;
        classes[newClassId] = Class(msg.sender, _teacher, _tokenAmount, _insuranceAmount, false);
        return newClassId;
    }

    function submitInsurance(uint256 _classId) public {
        Class storage class = classes[_classId];

        // Check that the function caller is the teacher in the class
        require(msg.sender == class.teacher, "Only the teacher can submit the insurance.");

        // Transfer insurance tokens from teacher to the contract
        require(transferFrom(class.teacher, address(this), class.insuranceAmount), "Insurance transfer failed.");
    }

    function completeClass(uint256 _classId) public {
        Class storage class = classes[_classId];

        // Check that the function caller is the student in the class
        require(msg.sender == class.student, "Only the student can complete the class.");

        // Check that the class has not been completed yet
        require(!class.completed, "Class already completed.");

        // Transfer tokens from student to teacher
        require(transfer(class.teacher, class.tokenAmount), "Token transfer failed.");

        // Return the insurance to the teacher
        require(transfer(class.teacher, class.insuranceAmount), "Insurance return failed.");

        // Mark the class as completed
        class.completed = true;
    }
}


DApp

이용자 인터페이스: 이용자가 토큰을 구매하고, 선생님을 선택하고, 수업을 예약하고, 피드백을 제공할 수 있도록 사용자 친화적인 인터페이스를 제공합니다. 이 인터페이스는 웹사이트 혹은 모바일 앱으로 제공될 수 있습니다.

선생님 인터페이스: 선생님이 자신의 계정에서 토큰을 관리하고, 수업을 수락하고, 학습 자료를 업로드하고, 피드백을 확인할 수 있도록 인터페이스를 제공합니다.

중개자 인터페이스: 중개자가 이용자와 선생님을 연결하고, 지불 및 보상 프로세스를 관리하고, 언어 능력 테스트, 일정 관리, 고객 지원 등의 서비스를 제공할 수 있도록 인터페이스를 제공합니다.


학생 인터페이스:
선생님 선택 및 수업 예약: 학생은 사용 가능한 선생님을 선택하고, 그 선생님과의 수업을 예약할 수 있어야 합니다. >> (아래 코드)

// Get a list of teachers
function getTeachers() {
    contract.methods.getTeachers()
        .call({ from: userAddress })
        .then(teachers => displayTeachers(teachers));
}

// Display teachers in a select box
function displayTeachers(teachers) {
    var selectBox = document.getElementById('teacherSelectBox');
    for (var i = 0; i < teachers.length; i++) {
        var option = document.createElement('option');
        option.text = teachers[i].name;
        option.value = teachers[i].address;
        selectBox.add(option);
    }
}

getTeachers();


선생님 인터페이스:
수업 수락: 선생님은 학생이 요청한 수업을 수락할 수 있어야 합니다. (>>아래 코드)

// Get a list of requested classes
function getRequestedClasses() {
    contract.methods.getRequestedClasses()
        .call({ from: userAddress })
        .then(classes => displayClasses(classes));
}

// Display classes in a select box
function displayClasses(classes) {
    var selectBox = document.getElementById('classSelectBox');
    for (var i = 0; i < classes.length; i++) {
        var option = document.createElement('option');
        option.text = classes[i].title;
        option.value = classes[i].id;
        selectBox.add(option);
    }
}

getRequestedClasses();


중개자 인터페이스:
결제 관리: 중개자는 학생이 선생님에게 지불한 토큰을 관리하고, 수업이 완료되면 선생님에게 토큰을 전송할 수 있어야 합니다. (>> 아래 코드)

// Get a list of all classes
function getAllClasses() {
    contract.methods.getAllClasses()
        .call({ from: userAddress })
        .then(classes => displayAllClasses(classes));
}

// Display all classes in a table
function displayAllClasses(classes) {
    var table = document.getElementById('classesTable');
    for (var i = 0; i < classes.length; i++) {
        var row = table.insertRow();
        row.insertCell(0).innerHTML = classes[i].title;
        row.insertCell(1).innerHTML = classes[i].status;
        row.insertCell(2).innerHTML = '<button onclick="releasePayment(' + classes[i].id + ')">Release Payment</button>';
    }
}

getAllClasses();



매칭 알고리즘

이용자의 학습 목표, 숙련도, 원하는 수업 빈도 등의 정보를 입력받아 선생님을 매칭하는 알고리즘을 구현합니다. 이 알고리즘은 이용자의 조건과 선생님의 조건을 비교하여 최적의 매칭을 찾아냅니다.
이 알고리즘은 DApp 내부에서 실행되며, 이용자와 선생님 사이의 매칭을 도와주는 역할을 합니다.
이러한 방식으로 DApp과 블록체인 네트워크를 구성하면, 블록체인 기반 언어학습 토큰생태계를 실현할 수 있습니다. 이 시스템은 이용자, 선생님, 중개자가 각자의 역할을 수행하면서 투명하고 안전한 방식으로 언어 학습을 진행할 수 있도록 합니다. 이 과정에서 스마트 컨트랙트와 블록체인 기술이 중요한 역할을 하며, 이를 통해 효과적인 언어 학습 환경을 제공할 수 있습니다.

// Define the list of teachers with more details
var teachers = [
    { name: 'Teacher 1', skills: { Korean: 5, English: 4 } },
    { name: 'Teacher 2', skills: { Korean: 3, English: 5 } },
    // Add more teachers...
];

// Define the student's learning goals in more detail
var studentGoal = {
    desiredSkills: { Korean: 4 },
};

// Function to calculate the matching score between a teacher and a student goal
function calculateMatchingScore(teacher, goal) {
    var totalScore = 0;
    var totalWeight = 0;
    for (var skill in goal.desiredSkills) {
        if (skill in teacher.skills && teacher.skills[skill] >= goal.desiredSkills[skill]) {
            totalScore += 1;
        }
        totalWeight += 1;
    }
    return totalScore / totalWeight;
}

// Find a matching teacher
function findMatchingTeacher(goal) {
    var bestMatch = null;
    var bestMatchScore = 0;
    for (var i = 0; i < teachers.length; i++) {
        var teacher = teachers[i];
        var matchScore = calculateMatchingScore(teacher, goal);
        if (matchScore > bestMatchScore) {
            bestMatch = teacher;
            bestMatchScore = matchScore;
        }
    }
    return bestMatch;
}

// Run the matching algorithm
var matchingTeacher = findMatchingTeacher(studentGoal);
if (matchingTeacher) {
    console.log('Matching teacher found:', matchingTeacher.name);
} else {
    console.log('No matching teacher found');
}


<!--
**hero-rq/hero-rq** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.
