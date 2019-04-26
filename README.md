//hackerRank
function timeConversion(s) {
    let modifier;
    let sec;
    let [hour, minutes, secound] = s.toString().split(":");
    secound.includes('PM') ? modifier = 'PM' : modifier = 'AM';
    secound < 10 ? secound = '0' + secound.toString() : '';
    sec = parseInt(secound)
    if (secound.toString().includes('PM') && hour.toString() != "12") {
        secound = parseInt(secound)
        secound < 10 ? secound = '0' + secound.toString() : '';
        hour = parseInt(hour) + 12
        sec = secound
    }
    if (secound.toString().includes('AM') && hour.toString() != "12") {
        secound = parseInt(secound)
        secound < 10 ? secound = '0' + secound.toString() : '';
        sec = secound
    }
    if (hour.toString() == "12" && modifier != 'PM') {
        hour = '00'
        secound = parseInt(secound)
        secound < 10 ? secound = '0' + secound.toString() : '';
        sec = secound
    }
    return hour + ':' + minutes + ':' + sec

}
