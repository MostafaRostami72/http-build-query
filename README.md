

# http build query in javascrpt



php http_build_query i n javascript




<pre>

function httpBuildQuery(object) {
    let query = '';

    Object.keys(object).forEach((key, index) => {
        const value = object[key];
        if (value && is_array(value) && value.length) {
            let and_index = index;

            for (let item of value) {
                query += ((and_index > 0) ? '&' : '') + key + '[]=' + item;
                and_index += 1;
            }
        } else if (value && !is_array(value) && typeof value !== "undefined" && !isEmpty(value)) {
            query += ((index > 0) ? '&' : '') + key + '=' + value;
        }
    });

    return query;
}


const obj = {
  a:a,
  b:b,
 }
 
 httpBuildQuery(obj) // output ?a=a&b=b

</pre>
