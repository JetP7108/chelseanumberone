/**
* @author CallmeSun
* @warn Vui lòng không sửa credits cảm ơn !
*/
module.exports.config = {
  name: "nambui",
  version: "1.0.0",
  hasPermssion: 0,
  credits: "CallmeSun",
  description: "Random Ảnh Thiếu Gia Nam Bùi Cực Bổ Mắt ( Lưu Ý Đây Là Lệnh Ảnh CỰC TỐN TIỀN, Cân Nhắc Trước Khi Sử Dụng)",
  commandCategory: "Random-img",
  usages: "nambui",
  cooldowns: 5,
  dependencies: {
    "request":"",
    "fs-extra":"",
    "axios":""
  }
};

module.exports.run = async({api,event,args,client,Users,Threads,__GLOBAL,Currencies}) => {
const axios = global.nodemodule["axios"];
const request = global.nodemodule["request"];
const fs = global.nodemodule["fs-extra"];
  var link = [
 "https://i.imgur.com/mV1DYXu.jpg",
 "https://i.imgur.com/Tv7q1HX.jpg",
 "https://i.imgur.com/FhQUdXz.jpg",
 "https://i.imgur.com/BBFRF4V.jpg",
 "https://i.imgur.com/tmkfqNP.jpg",
 "https://i.imgur.com/HD3N0LH.jpg",
 "https://i.imgur.com/fqUvm4p.jpg",
 "https://i.imgur.com/KVuESlj.jpg",
 "https://i.imgur.com/NKSzvTu.jpg",
 "https://i.imgur.com/IAPblsq.jpg",
 "https://i.imgur.com/IAPblsq.jpg",
 "https://i.imgur.com/ScBSEBb.jpg",
 "https://i.imgur.com/yoxfWvR.jpg",
  ];
  var max = Math.floor(Math.random() * 6);  
  var min = Math.floor(Math.random() * 2);
  var data = await Currencies.getData(event.senderID);
  var exp =  data.exp;
  var money = data.money
      if(money < 999) api.sendMessage("Bạn cần 999 đô để xem ảnh ?",event.threadID,event.messageID)
          else {
   Currencies.setData(event.senderID, options = {money: money - 999})
   var callback = () => api.sendMessage({body:`Suốt ngày ngắm NamBui😼\n» Số dư: -999 đô «`,attachment: fs.createReadStream(__dirname + "/cache/5.jpg")}, event.threadID, () => fs.unlinkSync(__dirname + "/cache/5.jpg")); 
      return request(encodeURI(link[Math.floor(Math.random() * link.length)])).pipe(fs.createWriteStream(__dirname+"/cache/5.jpg")).on("close",() => callback());
   }
};