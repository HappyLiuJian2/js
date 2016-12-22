var origin = {
	name : "apple"
};

var proxy = new Proxy(origin,{
	get : (target, property) => {
		return "I have an " + target[property];
	}
});

function Proxy_self(ori, option) {
	for (let key in ori) {
		//console.log(keys + ' ' + ori[keys])
		this[key] = ori[key];
	}

	if (!!option.get) {
		for (let key in this) {
			Object.defineProperty(this, key, {
				get : function() {
					return option.get(ori, key);
				}
			})
		}		
	}
};

var test = new Proxy_self(origin,{
	get : (target, property) => {
		return "I have an " + target[property];
	}
});

console.log(test.name);
