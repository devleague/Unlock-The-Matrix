# Unlock The Matrix

## Saturday fun challenge using Matrix Rotator:2advanced with http client

## Running

```
node matrix.server.js
```

_This will start up a node http server listening on port **1337**_

## Breaking the code

[Challenge-Rotate-Matrix:2advanced](https://github.com/devleague/Challenge-Rotate-Matrix/tree/2advanced) is required to complete this challenge.

Create a node program that loads MatrixRotator as a module.  

use npm to install your matrix rotator as a node_module.  
```
npm install -S https://github.com/[YOUR USERNAME]/Challenge-Rotate-Matrix#2advanced
```

Send http **POST** requests to your running `matrix.server` at `http://localhost:1337`.  
The **POST** Body only requires one field: `key` with value of your 2d array of hex values (as a urlencoded string).

For example, a 12x12 2d array:

```
[
  ['0x5F','0x6B','0x77','0x83','0x8F','0x8E','0x8D','0x8C','0x8B','0x8A','0x89','0x88'],
  ['0x53','0x11','0x12','0x13','0x14','0x15','0x16','0x22','0x2E','0x3A','0x46','0x87'],
  ['0x47','0x10','0x70','0x6F','0x6E','0x62','0x56','0x4A','0x3E','0x32','0x52','0x86'],
  ['0x3B','0xF','0x71','0x44','0x50','0x5C','0x68','0x67','0x66','0x26','0x5E','0x85'],
  ['0x2F','0xE','0x72','0x38','0x40','0x34','0x35','0x36','0x65','0x1A','0x6A','0x84'],
  ['0x23','0xD','0x73','0x2C','0x4C','0x41','0x42','0x37','0x64','0x1B','0x76','0x78'],
  ['0x17','0x19','0x74','0x2B','0x58','0x4D','0x4E','0x43','0x63','0x1C','0x82','0x6C'],
  ['0xB','0x25','0x75','0x2A','0x59','0x5A','0x5B','0x4F','0x57','0x1D','0x81','0x60'],
  ['0xA','0x31','0x69','0x29','0x28','0x27','0x33','0x3F','0x4B','0x1E','0x80','0x54'],
  ['0x9','0x3D','0x5D','0x51','0x45','0x39','0x2D','0x21','0x20','0x1F','0x7F','0x48'],
  ['0x8','0x49','0x55','0x61','0x6D','0x79','0x7A','0x7B','0x7C','0x7D','0x7E','0x3C'],
  ['0x7','0x6','0x5','0x4','0x3','0x2','0x1','0x0','0xC','0x18','0x24','0x30']
]
```

an example of the POST body

`key=0x5F,0x6B,0x77,0x83,0x8F,0x8E,0x8D,0x8C,0x8B,0x8A,0x89,0x88,0x53,0x11,0x12,0x13,0x14,0x15,0x16,0x22,0x2E,0x3A,0x46,0x87,0x47,0x10,0x70,0x6F,0x6E,0x62,0x56,0x4A,0x3E,0x32,0x52,0x86,0x3B,0xF,0x71,0x44,0x50,0x5C,0x68,0x67,0x66,0x26,0x5E,0x85,0x2F,0xE,0x72,0x38,0x40,0x34,0x35,0x36,0x65,0x1A,0x6A,0x84,0x23,0xD,0x73,0x2C,0x4C,0x41,0x42,0x37,0x64,0x1B,0x76,0x78,0x17,0x19,0x74,0x2B,0x58,0x4D,0x4E,0x43,0x63,0x1C,0x82,0x6C,0xB,0x25,0x75,0x2A,0x59,0x5A,0x5B,0x4F,0x57,0x1D,0x81,0x60,0xA,0x31,0x69,0x29,0x28,0x27,0x33,0x3F,0x4B,0x1E,0x80,0x54,0x9,0x3D,0x5D,0x51,0x45,0x39,0x2D,0x21,0x20,0x1F,0x7F,0x48,0x8,0x49,0x55,0x61,0x6D,0x79,0x7A,0x7B,0x7C,0x7D,0x7E,0x3C,0x7,0x6,0x5,0x4,0x3,0x2,0x1,0x0,0xC,0x18,0x24,0x30`

here's how the whole http **POST** message looks like
```
POST  HTTP/1.1
Host: localhost:1337

key=0x5F%2C0x6B%2C0x77%2C0x83%2C0x8F%2C0x8E%2C0x8D%2C0x8C%2C0x8B%2C0x8A%2C0x89%2C0x88%2C0x53%2C0x11%2C0x12%2C0x13%2C0x14%2C0x15%2C0x16%2C0x22%2C0x2E%2C0x3A%2C0x46%2C0x87%2C0x47%2C0x10%2C0x70%2C0x6F%2C0x6E%2C0x62%2C0x56%2C0x4A%2C0x3E%2C0x32%2C0x52%2C0x86%2C0x3B%2C0xF%2C0x71%2C0x44%2C0x50%2C0x5C%2C0x68%2C0x67%2C0x66%2C0x26%2C0x5E%2C0x85%2C0x2F%2C0xE%2C0x72%2C0x38%2C0x40%2C0x34%2C0x35%2C0x36%2C0x65%2C0x1A%2C0x6A%2C0x84%2C0x23%2C0xD%2C0x73%2C0x2C%2C0x4C%2C0x41%2C0x42%2C0x37%2C0x64%2C0x1B%2C0x76%2C0x78%2C0x17%2C0x19%2C0x74%2C0x2B%2C0x58%2C0x4D%2C0x4E%2C0x43%2C0x63%2C0x1C%2C0x82%2C0x6C%2C0xB%2C0x25%2C0x75%2C0x2A%2C0x59%2C0x5A%2C0x5B%2C0x4F%2C0x57%2C0x1D%2C0x81%2C0x60%2C0xA%2C0x31%2C0x69%2C0x29%2C0x28%2C0x27%2C0x33%2C0x3F%2C0x4B%2C0x1E%2C0x80%2C0x54%2C0x9%2C0x3D%2C0x5D%2C0x51%2C0x45%2C0x39%2C0x2D%2C0x21%2C0x20%2C0x1F%2C0x7F%2C0x48%2C0x8%2C0x49%2C0x55%2C0x61%2C0x6D%2C0x79%2C0x7A%2C0x7B%2C0x7C%2C0x7D%2C0x7E%2C0x3C%2C0x7%2C0x6%2C0x5%2C0x4%2C0x3%2C0x2%2C0x1%2C0x0%2C0xC%2C0x18%2C0x24%2C0x30
```

you may test it with curl  

`curl -d key=0x5F%2C0x6B%2C0x77%2C0x83%2C0x8F%2C0x8E%2C0x8D%2C0x8C%2C0x8B%2C0x8A%2C0x89%2C0x88%2C0x53%2C0x11%2C0x12%2C0x13%2C0x14%2C0x15%2C0x16%2C0x22%2C0x2E%2C0x3A%2C0x46%2C0x87%2C0x47%2C0x10%2C0x70%2C0x6F%2C0x6E%2C0x62%2C0x56%2C0x4A%2C0x3E%2C0x32%2C0x52%2C0x86%2C0x3B%2C0xF%2C0x71%2C0x44%2C0x50%2C0x5C%2C0x68%2C0x67%2C0x66%2C0x26%2C0x5E%2C0x85%2C0x2F%2C0xE%2C0x72%2C0x38%2C0x40%2C0x34%2C0x35%2C0x36%2C0x65%2C0x1A%2C0x6A%2C0x84%2C0x23%2C0xD%2C0x73%2C0x2C%2C0x4C%2C0x41%2C0x42%2C0x37%2C0x64%2C0x1B%2C0x76%2C0x78%2C0x17%2C0x19%2C0x74%2C0x2B%2C0x58%2C0x4D%2C0x4E%2C0x43%2C0x63%2C0x1C%2C0x82%2C0x6C%2C0xB%2C0x25%2C0x75%2C0x2A%2C0x59%2C0x5A%2C0x5B%2C0x4F%2C0x57%2C0x1D%2C0x81%2C0x60%2C0xA%2C0x31%2C0x69%2C0x29%2C0x28%2C0x27%2C0x33%2C0x3F%2C0x4B%2C0x1E%2C0x80%2C0x54%2C0x9%2C0x3D%2C0x5D%2C0x51%2C0x45%2C0x39%2C0x2D%2C0x21%2C0x20%2C0x1F%2C0x7F%2C0x48%2C0x8%2C0x49%2C0x55%2C0x61%2C0x6D%2C0x79%2C0x7A%2C0x7B%2C0x7C%2C0x7D%2C0x7E%2C0x3C%2C0x7%2C0x6%2C0x5%2C0x4%2C0x3%2C0x2%2C0x1%2C0x0%2C0xC%2C0x18%2C0x24%2C0x30 localhost:1337 2>/dev/null | python -m json.tool`
