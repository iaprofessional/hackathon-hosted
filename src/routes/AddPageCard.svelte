<script>
  let customAttribute = false;

  function toggle1() {
    console.log("Onclick");
    console.log(customAttribute);
    // Function to toggle the visibility of elements based on 'checked'
    if (customAttribute == false) {
      c1Visible = "none";
      c2Visible = "inline";
      customAttribute = true;
    } else {
      c1Visible = "inline";
      c2Visible = "none";
      customAttribute = false;
    }
  }

  // Variables to control the visibility of the elements
  let c1Visible = "none";
  let c2Visible = "inline";
</script>

<div>
  <div class="card">
    <center>
      <h1>Buyer or Seller?</h1>
      <br />
      <div class="form-check">
        <label class="form-check-label">
          <input
            class="form-check-input"
            type="checkbox"
            id="check1"
            name="option1"
            value="something"
            checked={customAttribute}
            on:click={toggle1}
          />
          Seller
        </label>
      </div>
    </center>
    <center id="c1" style="display: {c1Visible};">
      <br />
      <h2>Book's Title</h2>
      <br />
      <input
        id="i1"
        class="form-control input-sm"
        style="border-width: medium; border-color: black; width: 80%;"
        placeholder="Percy Jackson and the Sea of Monsters"
      />
      <br />
      <h2>Book's Image</h2>
      <br />
      <button style="height:100px; width:100px;"
        ><img
          style="height:50px; width:50px;"
          alt="alter"
          src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBxAPEA4PDw4VEhUQFRYVEBEYEBUVEBYSFxUWFhoVFxUbHSgiGRolHRUWIjIiJSkrLi4uGB8zODMtNy4tLi0BCgoKDg0OGxAQGy0lHyYxLSsrKy0rKy0tLTYvLS0tLS0tLS0tLS8tLS0tLS0tLS0tLS0tMS0tLS0tLS0tLS0rL//AABEIAOEA4QMBIgACEQEDEQH/xAAcAAEAAQUBAQAAAAAAAAAAAAAABwIDBAUGAQj/xABSEAACAQIBBwUGDw0IAwAAAAAAAQIDBBEFBhIhMUFRBxNhcaEiMnKBkbEWFyM1QlJUVWKDkpOzweMUNFNzdIKUoqSywuHwJTNDY2XR0tMVJET/xAAaAQACAwEBAAAAAAAAAAAAAAAABQIDBAEG/8QAOREAAgEBAgoJAwQCAwEAAAAAAAECAwQRBRIhMUFRYYGh0RMUMlJxkbHB4SIz8BUjNLKi4mJj8UP/2gAMAwEAAhEDEQA/AJxAAAAAAAAAABTKSSbbwS2vdgcjlzPqhRxhQXPT444Uk/C3+LV0llKjOq8WCv8AzSVVa0KUcabu/NGs680OU87LK3xUq2nJewgtN9WPep9bI0yrl+6u2+drNx3U49zD5K29pqxrSwWllqPcuYqrYVeanHe+Wjz3HdXvKJN4qhbxXCUpOX6scMPKzR3WeF/U/wDo0FwjBRXlwx7TRg3QslGGaK9fUwTtleeeb3ZPTmZlXLFzPvrmrLrqya8mJiSqSe2TfW2zwF6ilmRQ5Sed3iM2tja6ngZVLKtzDvbipHqqyXmZigGk84KUlmZurbO2/p7LiUlwcYz7Wse03VpyiVY4KrbRmuMZOD8jxT7DiwUzstGfaivTisvEuha68M03vd/reSvk3POzrYRdR0pP2NRaK+UsY+VnRU5qSTi009jTxT8ZAxm5MytcWrxoVpR4xxxi+uL1ePaYauC4v7bu2P8AL+DN9LCslkqRv2rl8om8HEZEz+pzwhdQ5p+3WLg+tbV2+I7KjVjOKnCSlGSxjJNOLXFNbRVWoVKTumrhrSr06qvg7/XyLoAKi4AAAAAAAAAAAAAAAAAarLWW6NnDTrS1vvYLXOT6Fw6XqMDOnOanZR0I4TrSXcw3RXtp9HRtfaRbe3lSvUlVrTc5S2t+ZLcuhDCyWF1frnkjxfJbRda7eqLxIZZenN7PPbtMv5zXF42m9CnupRfc+N+yfZ0GlAHsIRhHFirkIZ1JTljSd7AAJEAAAAAAAAAAAAAAAAABssi5euLOWNKfct91SeuEvFufSjWg5KKksWSvRKMpQeNF3Ml/N/OOheRwi9GoljOk33S6Yv2Ueny4G9IFo1ZQlGcJOMovGMk8JJ8UyTM0s7Y3KjRuGo1vYvZGp1cH0b93BI7XYHT+unlWrSua2j2x4QVR4lTJL15PYdcABaMwAAAAAAAAAAc3nbnHGyhowwlWqLuI7orZpy6OC3vxmfl/K0LOhKtPW9kI465TexdW9vgmQ9fXlSvUnWqy0pzeMn9S4JbEhhYbJ0rx59lcfhafIXW+2dCsSHafD5ejz8bdetKpKU5ycpSeMpN4tviUgD88+AABwAAAAAAAAAAAAAAAAAAAAAAAB4m0008Gtaa1NPimegAJMzKzoVylQry9Viu5l+Eiv4lv47eJ2BAlOpKEozjJxlFpxkng01rTRLmaeXle0cZYKrDBVY+aS6H2PFCK32RU/wByGbStXwPsH2zpP2559D1/Pqb8AC0aAAAAKZSSTbeCW17sCo4/lDyvzNBUIPu6+OPFU1t8uzq0iyjSdWahHSVVqsaUHOWj8uOOzty27y4bT9Tp4xpLo3y65YeRI0gB6mEIwioxzI8rUnKcnKWdgAEiAAAAAAAAAAAALtlaTr1KdGnHSnUeEV2tvoSTb6EwbSV7OpNu5FoFy7tp0ak6VSOjKDakun/bfj0lsE78qBq7IwAAOAAAAAAAAAAAzsh5VnZ14Voa8NU4+2i9sfrXSkYIOSipJxeZkoycWms6J1ta8KsIVKb0ozSlF8U9ZfOA5Ncsap2c3sxlR/ij/F42d+eXtFF0ajh5eGg9TZ6yrU1Nb/HSAAUl54QtnJlJ3V1Wq49zjo0/Ajqj5f4mSXnplD7nsq0k8JVPU4ccZ7cOlRUn4iIBzgulkdR+C9xLhWtljTXi/b34FQAGwnAAAAAAAAAAABarVYwi5SeCX9YAdPatVQWlL/dt8Et7JRzEzcdrT5+vHCvWXe/gqb1qn4T1OT44LcmczybZtyuJxylcxwhB/wDqU3sbX+M10bunXuWMqiO32vHfRwzado9wfY8RdJPPo2f+nI575ufdMOfpR9VprWltnBbvCW7xrhhF5PxGufub3NSd3Rj3En6rFexm3t8GT7evVZg61f8Axlu5cvLSivCVkv8A3ob+fPZl0HGgAcCUAAAAAAAAAAAAAL2T7yVCrTrQ76nJSXThtXU1ivGTfa3EatOFWDxjOKlF9DWKIKJN5OL/AJy1lRb10JYfmzxlHt0l4hZhSljU1UWjJufz6jTBdXFm6bzPLvXNeh14AEY+I75ULzGdvQT2Rc5Lwnox/dflOHN7nzcc5f3HCGjFfmpY9rkaI9PZIYlGK2X+eU8tbJ49eb23eWTmAAaDMAAAAAAAALdWqoJyk8EgOnlarGEXKTwS/rAyczsgTyvc41E429Fp1Hsx4U0/bS3vcvEcve3UqrxepLvY8P5nRZFz9u7OjC3oUqEYQx205uUpPbKT09bf9ahdaqs5xupjKy0oQeNU/NhPNGlGEYwjFRjFJRilgkksEktyLpCHpq5S9pQ+Zn/2ElZg5arX9lG4r6Om5zj3EXGOEXgtTbE86E4K9jqFeE3dE6UtV6MakZQnFSjJNSi9jT1NM1GeWU6lpY3FzR0dOkouOkm465xi8Umtze8iz01cpe0ofMz/AOw5Tozmr4hUrQg7pGXnTkKVlWa1unPF0p9G9P4S7dTNOZ9bPG9v6Thc06PN4pxapSU9Jb4vTeG9Y9LRgHpLPKpKmnUz+u388dJ5q0xpxqPo3k9Nn54aAAC4zgAAAAAAAAAA6nk4vObu3Sb1Voyjh8KPdrsT8pyxnZBuOaurep7WpHHwXJJ9jZVXhj05R1pl1nniVYy2r5JuAB5S89dikH5bqad1cy9tVm/1pGGe1ZYyk+Lb8rPD18VckjxsnfJvWAAdIgAAAKWzyckk23gkb3kwuXPKPBKlUwXjjrfSVV6ypQcs+wvoUXWmo33bTn6teME5Skkl0mjvLznHi2klsWOz+Z9PAU1MJ4+TFyePwNqeDFDLjZfD5PlhyXFeUpclxXlPqkFPXV3ePwXqw/8ALh8nyuTlyR+tkPxtX94g2OxE5ckfrZT/ABtX94stnY3lVj7e73RncpXrVe+DD6WBB+TrDTwnPvdy9t/InjPympZPuoyWKahivjIEM3t3GlHi33sfr6i3B0Ium5SzJ+yKcIzkpqMc7Xuy/ilq1Iaa4ryki8j1VzsKkpPFu4qfuwO6LJ4TUZOOJm2/BCngrHipY+f/AI/7EAaa4oaa4on8Ef1Zdz/L4J/pH/Z/j/sQCmnsZUd1yqd/ZdVXz0zhRjQq9LTU7rr+bXsLLRS6Ko4X33btCe3WAAWlIAAAClvgVFJ1O5g1eiY//PLoBF//AJOXECf9NQ8/VDXTjg2uDaBlZZp6FzcR9rUmvJKSMUbJ3q8SyV0mgADpEFEpJJt7EeykksWa65rOb6FsRGUsUnCGMy3dV3N8Eti+tnWck/rh8VU88TkGjsOShf2h8VPzxF9pbdOTeoY2RJVYpayZiLs8c+r2zvbi3oqnoU9DR0qbcu6pwk8XpLfJkokE8pi/tS7+K+hpiyyQjKbUlfk90NLXOUIJxd2X2ZlvlQyjwo/My/5Hj5Uco8KPzMv+ZxrRQ0b+r0u6hf1mr3mWsCcOSL1sh+Nq/vEItE38knrZD8bV/eKbZ9veXWL7m73RseUGroZNvJ4Y4Rjq+MgfPtWo5tyk8WyfuUr1qvfBh9LAgAjY2+ja2+yO2xLpE9nuzo83s9bzJ9F0Lfm9Fyc+6puUtJpJ69JatSNp6amUf8n5mX/M4gFzpQbvaKlWqJXKRIWSOUq/q3NtSnzWjVrUoSwpNPRnOMXg9LbgyZT5pzb+/bH8oofSwPpYxWqEYtKKN1lnKcW5Mj3lU7+y6qvnpnCndcqnf2XVV89M4UdWD+PHf/ZiPCH8mW7+qAANZjAAAAUlRRLYzqysG7kZ/wBwS4dgJL9DvwUBV+oxHH6ZI4LPS35u/uVulJSX50U324mlO05T7XRq21VLVOLi+uLxXZLsOLNtlnj0Yy2emT2F9rhiV5rbf55fcFMnhrYbwMStPS6uBc3cUqN7KK9Vy6tyLDRdaKWih5S9ZC20dhyU+uHxU/PE5Bo7Dkr9cPip+eJmtH2peBqsv3okxkFcpfrpd/FfQ0ydSDOUlf2pd/FfQ0xdYfuPw90Mrf8AbXj7M5Vo8aK2iloZipMttEkcmGdtvbUZWd1UVLu3OlUf921LDGMpexaabxerX5Y6aKGiqrTVSOKy6lVdOWMiU+UnPG2qWs7O2qqtKs46c4vGnCEZKXfbG24pYLp2asYmaK2jxohTpKnG5EqlV1JXspAaBMgbHNv79sfyih9LA+lj5pzb+/bH8oofSwPpYwWztLwGFi7L8SPeVTv7Lqq+emcKd1yqd/ZdVXz0zhRxYP48d/8AZibCH8mW7+qAANZjAAAAZeRrfnbm3p+3nFPq0lj2YmIdLyeWnOXsJ4aqMXJ8MWtFefHxFdaeJTlLUn8cS6hDHqxjra+eBK4APKXHrsZnN5+WHPWdRxXdUWqkepYqX6rk/ERK2T3OCknFrFNYNbmnuIOy9k+VtcVqD/w5anxg9afka7Rzgut9LpvRlXv7eYjwpR+qNRacj9vfyNbUliW2i40UtDFi1FDRQ0XGjxoiSLTR1vJZ64fFz86OUaOu5Lfv/wCLn50Z7V9mXgarJ96PiTAQdykeul38V9DTJxNTeZvWdacqla1pznLDSlKCcngkli+pJCez1lSk29V3oOLTRdWCinpv4Ne58+NFLR9AehTJ/uKl8hHvoUyf7ipfIRs6/DU+Bj/T5d5Hz40UtH0J6E8n+4qXyEeehLJ/uGj82iLt0NT4HeoS7yPnpooaPoj0I5O9w0fmkPQhk73BQ+aRzrsdT4Heoy1rifOzRS0fRXoQyd7go/NRHoPyd7gofNROdcjqfAl1KWsgbNv79sfyih9LA+ljR0c1MnwlGcLGjGUGpRkqaTUk8U10po3hmr1VUaaNNCk6aabI95VO/suqr56Zwp3XKp39l1VfPTOFHtg/jx3/ANmIMIfyZbv6oAA1mMAAABJHJpYaFCpcNa60sI+BDFedvyIjq2oSqzhTgsZVJKMV0t4LxE35PtI0KVKjDZTiorpwW3re0W4Tq4tNQ1+i+fQaYLpY1RzehcX8X3+JlAARD4HC8peRucpwu4LXS7mp0wb1PxN/rdB3Rar0YzjKE4qUZpxlF7HFrBpltGq6VRTRVXpKrTcHpIBaKGjcZyZGlZXE6Lxce+pS9tF7PGtj6jVNHpoyUkpLMzzEouLcZZ0WmilouNFLRxoCho2ebOWvuC4+6Oa5zuJR0dPQ77DXjg+HA1rR40VyipJp5mWQk4yUlnRIPpqP3B+0/Znnpqv3v/afsiPGilozdTod3i+Zp67X73BciRPTXfvev0r7M89Nh+96/SvsiOWjxo51Sj3eL5klbK/e4LkSN6bL971+lfZHnptf6ev0r7IjhooaI9Uo93i+ZLrlbvcFyJJ9Nx+937V9keem7/p37V9kRq0UtHHZaPd4vmdVrrd7guRJfpvP3u/avsjx8r797l+l/ZEaNFDRHqtLu8XzJdard7guRJvpvv3tX6X9kePlifvb+1/ZEYNG0ydYYYTmvBj9bOxsdOTuUeL5nJW2pFXuXBcjq84M5ZZS5icrbmObUsI87zjalo633McO96dpqABpTpxpxUI5kKqlSVSbnLOwACZWADIybYTua1OhTXdTeGO5LfJ9CWsG0lezqTbuR1vJtkjSqTu5rVDGNLpm13UvEnh+c+BI5iZNsoW9KFGmsI01guLe9vpbxfjMs8vaazrVXPy8PzLvPU2Wh0NNQ06fH8ybgACg0AAABos6shRvqDhqVSGMqUuEt8X8F4YPxPcQ7XoyhKUJxcZQbUovamtqZP5x+e2a6uouvRj6tFa4/hIrd4S3Pfs4YMbDa1TfRzzPNs+Bbb7J0i6SGdZ9vytBFjRQ0XZRabTWDWpp6mnwaKWh2I0y00UtFxopaItEihooaLjR40RJFpooaLrRS0RJFtopaK2jxoiSTLTRS0XWihoiSLbR40VtGfZWeyc14K+thGDk7kEpqKvZTYWOGE5rwY/WzZAGuMVFXIxyk5O9gAEiIAKQAqRKmZWb33JS5yovVqq7r4MNqj17309Rqsxc13HRu7iOEttCm1s+HJceC3bduGHeiXCFrUv2oZtL9uY8wdY8X92efQtW3fo1AACobAAAAAAAAAAHHZ35oRudKvbpRreyjsjU/wBpdO/fxIwq0pQlKE4uMovCUWsJJrc0fQBz+cubFG9Wk+4qpYRqpa+qS9ku1bhlZLd0axKmbQ9Qstdg6T66efStfyQ40UNG0y1kWvZz0K8MMe9mtcJeDL6nrNa0OU01enehM04u5q5ltopaLjRS0caAoaKGi40eNESRaaKGi60UtESRbaKWitoy7W29lLxL62Ci2dckkU2lpslJdS+tmcAaIxUVcjNKTk72AAdIgAyMnZPrXM1ToU3OW/DYlxk9iXWDaSvZ1Jt3Ix0d/mhmdouNxdx7pa6dF7uEprjwju369S2ubOaNK0wq1MKtb22Hcx8FPf8ACevqOoEtrwhjLEpZtL5cx3Y8HYv11c+havHX4AACobAAAAAAAAAAAAAAAAAWLq2p1YOnVhGcZbYySafiOEy5ye7Z2U8P8mT1dUZfU/KSEC6jaKlF3we7R5fjKa1np1l9a36fMgO/sKtvLQr0pU5blJYY9T2SXSjFaJ/uraFWLhUhGcXtjKKlHyM5TKfJ9a1cXRlKg+C7uHyXr8jQ0p4Sg8k1dxXP1FVTBk49h38HyfAilopaOwyhye3lPF0nGst2jLRn8l4LtZobvId3Sx5y1qRw36EnH5SWHabI1ac+zJPeY50KkO1F+XuaxooaK5NLUy9Ro734kWYrKsdHlvQ9k/EjKKTzSXEtjG7MVSllvZWDMtsk3FX+7t5z6VB4eXDA3FjmNe1MNOKpL4UlJ+SOPbgVzrU4dqSW/wBs5ZToVanZi3ud3nmObK7a3nVkoU4SnJ7Ixi5S8i3Ei5N5P6EMOfqOq1uXqcext9qOqsrGlQjoUaUaa4RSWPS+L6zDVwnTj2Fe/Jc/Q30sF1JZZtLi+W/KcDkTMGcsJ3c9Bfgk05vrlsj4sfEd7YWFK3gqdKmoRW5bW+Le1vpZlgU1rTUrdt7tH543jahZadHsLLr0/nhcAAUGgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAZ2Oc0OcuwjPK3fMAcYNzCjChZyd3yJLzY9j1AE8I9krwXnOlAAkQ8lnAAAiAAAAAAAAAAAAAAAAB//2Q=="
        /></button
      >
      <br />
      <h2>Book's price</h2>
      <br />
      <input
        id="i2"
        class="form-control input-sm"
        style="border-width: medium; border-color: black; width: 80%;"
        placeholder="Rs. 500"
      />
      <br />
      <h2>Contact</h2>
      <br />
      <input
        id="i3"
        class="form-control input-sm"
        style="border-width: medium; border-color: black; width: 80%;"
        placeholder="+91 xxxxxxxxxx"
      />
      <br />
    </center>
    <center id="c2" style="display: {c2Visible};">
      <br />
      <h2>Book's Title</h2>
      <br />
      <input
        id="i1"
        class="form-control input-sm"
        style="border-width: medium; border-color: black; width: 80%;"
        placeholder="Percy Jackson and the Sea of Monsters"
      />
      <br />
      <h2>Your Contact</h2>
      <br />
      <input
        id="i2"
        class="form-control input-sm"
        style="border-width: medium; border-color: black; width: 80%;"
        placeholder="+91 xxxxxxxxxx"
      />
      <h2>Book's Price</h2>
      <br />
      <input
        id="i3"
        class="form-control input-sm"
        style="border-width: medium; border-color: black; width: 80%;"
        placeholder="Rs. 500"
      />
      <br />
    </center>
  </div>
</div>
