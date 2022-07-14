# CSS สร้างหน้ากระดาษสำหรับ printer

```css
@page {
  margin: 0
}

body {
  margin: 0
}

.sheet {
  margin: 0;
  overflow: hidden;
  position: relative;
  box-sizing: border-box;
  page-break-after: always;
}

/** Paper sizes **/

body.A3 .sheet {
  width: 297mm;
  height: 419mm
}

body.A3.landscape .sheet {
  width: 420mm;
  height: 296mm
}

body.A4 .sheet {
  width: 210mm;
  min-height: 296mm
}

body.A4.landscape .sheet {
  width: 297mm;
  height: auto
}

body.A5 .sheet {
  width: 148mm;
  height: auto
}

body.A5.landscape .sheet {
  width: 210mm;
  height: auto
}

/** Padding area **/

.sheet.padding-10mm {
  padding: 10mm
}

.sheet.padding-15mm {
  padding: 15mm
}

.sheet.padding-20mm {
  padding: 20mm
}

.sheet.padding-25mm {
  padding: 25mm
}

/** For screen preview **/

@media screen {
  body {
    background: #e0e0e0
  }
  .sheet {
    background: white;
    box-shadow: 0 .5mm 2mm rgba(0, 0, 0, .3);
    margin: 5mm;
  }
}

/** Fix for Chrome issue #273306 **/

@media print {
  body.A3.landscape {
    width: 420mm
  }
  body.A3, body.A4.landscape {
    width: 297mm
  }
  body.A4, body.A5.landscape {
    width: 210mm
  }
  body.A5 {
    width: 148mm
  }
}
```
