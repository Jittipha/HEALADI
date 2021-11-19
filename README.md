# <h1>HEAL A DI</h1>
<h3>โปคเจคเว็บแอปสำหรับคำนวณแคลอรี่ จัดทำโดย นาย จิตติพัฒน์ วงศ์ภูมิ</h3>
<h2>Features</h2>

<ul>
  <li>คำนวณแคลอรี่</li>
  <li>บันทึกมื้ออาหาร</li>
  <li>ดูจ้อมูลโภชนาการของอาหาร</li>
 </ul>
  
<h2>Example code</h2>


        body {
            margin: 0;
            background: linear-gradient(45deg, #49a09d, #5f2c82);
            font-family: sans-serif;
            font-weight: 100;
        }

        table {
            width: 800px;
            border-collapse: collapse;
            overflow: hidden;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        }


        tr,
        td {
            padding: 15px;
            background-color: rgba(255, 255, 255, 0.2);
            color: #fff;
        }

        td {
            text-align: center;
            color: #000;
        }


        td {
            background-color: #55608f;
        }

        .imge {
            text-align: center;
            margin-top: 20px;
        }

        .row {
            margin-top: 10px;
        }
    </style>




</head>

<body>
    
    <div class="imge">
        <img src="https://www.calforlife.com/public/assets/image/icon/gymnast_men.png" width="80px;" height="80px;" style="margin-right: 3rem;">

        <img src="https://www.calforlife.com/public/assets/image/icon/gymnast_women.png" width="80px;" height="80px;"><br><br><br>

    </div>


    @using (Html.BeginForm("Cal", "Home", FormMethod.Post))
    {
        <div class="container">
            <p>เพศ</p>
            <div id="12" class="form-check form-check-inline">
                @Html.RadioButton("sex", "Male")<text>  ชาย</text>
                @Html.RadioButton("sex", "Female")<text>  หญิง</text>
            </div>
            <div class="row">
                <p class=" col-sm-2">อายุ(ปี)</p>
                <input required type="text" name="age" placeholder="Please your age." class="form-control col-sm-10" />
            </div>
            <div class="row">
                <p class=" col-sm-2">น้ำหนัก(กิโลกรัม)</p>
                <input required type="text" name="Weight" placeholder="Please your weight(KG)." class="form-control col-sm-10" />
            </div>
            <div class="row">
                <p class=" col-sm-2">ส่วนสูง(เซนติเมตร)</p>
                <input required type="text" name="Height" placeholder="Please your height(CM)." class="form-control col-sm-10" />
            </div><br>
            <div class="input-group mb-3">
                <label class="input-group-text" for="inputGroupSelect01">เป้าหมาย</label>
                <select class="form-select" name="Target" required>
                    <option selected>--เป้าหมาย--</option>
                    <option value="500">ลดน้ำหนัก</option>
                    <option value="0">สร้างกล้ามเนื้อ</option>
                </select>
            </div>
            <div class="input-group mb-3">
                <label class="input-group-text" for="inputGroupSelect01">ออกกำลังกาย ต่อสัปดาห์</label>
                <select class="form-select" name="Exercise" required>
                    <option selected>--DAY--</option>
                    <option value="1.2">-Never-</option>
                    <option value="1.375">1-3</option>
                    <option value="1.55">3-5</option>
                    <option value="1.7">6-7</option>
                    <option value="1.9">-Everyday-</option>

                </select>
                <button type="submit" class="btn btn-primary">คำนวณ</button>
            </div>
        </div><br>
    }

    <div class="table-container">
        <table class="table">

            <tr>
                <td>แคลอรี่</td>
                <td>โปรตีน(กรัม)</td>
                <td>คาร์โบไฮเดรต(กรัม)</td>
                <td>ไขมัน(กรัม)</td>
            </tr>
            @if (Model != null)
            {
                foreach (var item in Model)
                {
                    <tr>
                        <td>@item.Calforday</td>
                        <td>@item.Protein</td>
                        <td>@item.Carbohydrate</td>
                        <td>@item.Fat</td>
                    </tr>
                }
            }
        </table>
    </div>



</body>

</html>


<h2>Credit</h2>
<h3>610107030015@dpu.ac.th</h3>
<h2>License</h2>
<h3>Nanine</h3>

