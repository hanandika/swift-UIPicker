1. add IBOutlet and array Object for picker
```
@IBOutlet weak var satuanInput: UITextField!
let myPickerData = [String](arrayLiteral: "Liter", "Kilogram")
```

2. init Picker in viewDidLoad()
```
let thePicker = UIPickerView()
thePicker.delegate = self
satuanInput.inputView = thePicker
satuanInput.text = "Liter"
```

3. add extension for UIPickerViewDelegate and UIPickerViewDataSource 
```
func numberOfComponents(in pickerView: UIPickerView) -> Int {
    return 1
}

func pickerView(_ pickerView: UIPickerView, numberOfRowsInComponent component: Int) -> Int {
    return myPickerData.count
}

func pickerView( _ pickerView: UIPickerView, titleForRow row: Int, forComponent component: Int) -> String? {
    return myPickerData[row]
}

func pickerView( _ pickerView: UIPickerView, didSelectRow row: Int, inComponent component: Int) {
    //set value text to textfield
    if myPickerData[row] == "Liter" {
        self.labelSatuan.text = "Harga per Liter"
    } else {
        self.labelSatuan.text = "Harga per Kilogram"
    }
}
```
