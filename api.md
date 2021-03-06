# API
Para a implementação dos testes de frontend e mobile será necessário consumir os seguintes serviços com os respectivos contratos:

### Receber informações sobre o usuário (professor)


##### GET https://api-test.miraeducacao.com.br/teacher/{teacherId}
```json
{
   "id": "ecc9a6ed-2456-4f21-8909-60535ed1670b",
   "name": "João Ferreira"
}
```

### Receber listagem de turmas

##### GET https://api-test.miraeducacao.com.br/teacher/{teacherId}/schoolclasses
```json
[
   {
      "id": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
      "teacherId": "ecc9a6ed-2456-4f21-8909-60535ed1670b",
      "discipline": "Geometria",
      "level": "6º ano",
      "term": "B",
      "period": "Manhã"
   },
   {
      "id": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
      "teacherId": "ecc9a6ed-2456-4f21-8909-60535ed1670b",
      "discipline": "Física",
      "level": "8º",
      "period": "Noturno",
      "term": "C"
   }
]
```

### Receber a listagem de alunos de uma turma

##### GET 	https://api-test.miraeducacao.com.br/students?schoolClassId={schoolClassId}
```json
[
   {
      "id": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
      "schoolClassId": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
      "orderId": "1",
      "name": "João de Barro"
   },
   {
      "id": "4bbb5158-e60a-4c96-9a3e-ac360b6632f3",
      "schoolClassId": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
      "orderId": "3",
      "name": "Mário Roberto"
   },
   {
      "id": "9d395096-e02d-11e7-80c1-9a214cf093ae",
      "schoolClassId": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
      "orderId": "4",
      "name": "Rosana Silva"
   },
   {
      "id": "a243b392-e02d-11e7-80c1-9a214cf093ae",
      "schoolClassId": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
      "orderId": "16",
      "name": "Humberto Ramos"
   },
   {
      "id": "4324fsfd-cfsafas-4fasa2-8fs21-sasf",
      "schoolClassId": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
      "orderId": "8",
      "name": "Maria Alberta"
   }
]
```

### Inserir uma chamada de uma turma

##### POST 	https://api-test.miraeducacao.com.br/schoolclass/{schoolClassId}/lesson
```json
{
   "id": "10ff4245-4621-42f3-9c75-e10244f43134",
   "date": "2016-09-13T13:30:52.123Z",
   "schoolClassId": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
   "lessonOrder": 1,
   "attendances": [
      {
         "studentId": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
         "status": "PRESENT"
      },
      {
         "studentId": "4bbb5158-e60a-4c96-9a3e-ac360b6632f3",
         "status": "PRESENT"
      },
      {
         "studentId": "4324fsfd-cfsafas-4fasa2-8fs21-sasf",
         "status": "ABSENCE"
      }
   ]
}
```

### Atualizar uma chamada de uma turma

##### PUT 	https://api-test.miraeducacao.com.br/schoolclass/{schoolClassId}/lesson/{lessonId}
```json
{
   "id": "10ff4245-4621-42f3-9c75-e10244f43134",
   "schoolClassId": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
   "date": "2016-09-13T13:30:52.123Z",
   "lessonOrder": 1,
   "attendances": [
      {
         "studentId": "e8c6d161-c8d1-4e90-8e0f-affd06ac005c",
         "status": "PRESENT"
      },
      {
         "studentId": "4bbb5158-e60a-4c96-9a3e-ac360b6632f3",
         "status": "ABSENCE"
      },
      {
         "studentId": "4324fsfd-cfsafas-4fasa2-8fs21-sasf",
         "status": "PRESENCE"
      }
   ]
}
```

> Para efeitos de simplicidade, não há necessidade de autenticação nem autorização para consumo dos serviços.
