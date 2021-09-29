# practice_proxy

const obj = {name: "Abhi"}
Object.freeze(obj);
function getTimestamp(){ return new Date().getTime();}
const getHandler = {
  get(target, property){
    console.log("GET" + getTimestamp()); 
    return target[property];
  }
}
const getProxy = new Proxy(obj, getHandler);
console.log(getProxy.name)

const setTrap = {
  set(target, property, value){
    console.log("SET " + getTimestamp() + " Property: "+ property + " value:" + value);
    if(!target[property]) throw new Error("Property doesnt exist.")
    return target[property]=value;
  }
}

setProxy.name="testAbhi"
setProxy.lastName = "Makker"

console.log(setProxy.name)
console.log(setProxy.lastName)
