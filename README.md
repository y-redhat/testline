const wait = (ms) => new Promise((resolve) => setTimeout(resolve, ms));
const apiUrl = 'https://your-service.onrender.com/api/endpoint'; // 引用符が必要

async function getData() {
  while (true) { // for(true) ではなく while(true)
    try {
      const response = await fetch(apiUrl);
      const data = await response.json();
      console.log(data);
      await wait(2000); // 20秒待機
    } catch (error) {
      console.error('エラー:', error); // 引用符が必要
      await wait(2000); 
    }
  }
}

getData();
