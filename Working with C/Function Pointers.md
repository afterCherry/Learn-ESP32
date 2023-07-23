# Function Pointer
- Function wras functions
- Function Pointer as a parameter *DoWork, almost like variables

```C++
typedef struct Person_struct
{
  ...
  void (*DoWork)(char *dataRetrieved)
} Person;

void updatePerson(Person *person, char * dataRetrieved)
{
  strcpy(person->firstName, "data from dataRetrieved");
  strcpy(person->lastName, "data from dataRetrieved");
  person->age = 35;
}

void connectAndGetInfo(char * url,void (*DoWork)(char *dataRetrieved))
{
  //connect to wireless
  // connect to endpoint
  // allocate memory
  char *dataRetrieved = (char *)malloc(1024);
  // fill buffer with data: getRequest(&dataRetrieved);
  // do work and get a person object
  DoWork(dataRetrieved);
  // clean up memory and other resources
  free((void *)dataRetrieved);
}

void DoWorkForPerson(char *dataRetrieved)
{
  ...
}

void app_main(void)
{
  connectAndGetInfo("http://getperson.com",DoWorkForPerson);
}

```






# Words
- signature of a function: 只包括函数的名称、参数类型和返回值类型。
- generic 通用的
- malloc return a void pointer
- grab the memory 抓住存储
- a chunk of 一大块
- kilobyte KB
- pseudocode 伪代码
- inflammation 炎症
