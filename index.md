## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/0xBEFE/pe_header_site/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/0xBEFE/pe_header_site/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.





<tbody>
<tr>
	<th>Offset
	</th>
	<th>Size
	</th>
	<th>Member
	</th>
	<th>Meaning
	</th>
</tr>
<tr>
	<th colspan="4">
	<h3><span id="Image_File_Header_(0x00)"></span><span class="mw-headline" id="Image_File_Header_.280x00.29">Image File Header (<tt>0x00</tt>)</span></h3>
</th>
</tr>
<tr valign="top">
<td><tt>0x00</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Signature
</td>
<td>PE Magic Value
</td></tr>
<tr>
<td><tt>0x04</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>Machine
</td>
<td>For a list of values, see <a href="#Machine_Types">machine types section</a>
</td></tr>
<tr>
<td><tt>0x06</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>NumberOfSections
</td>
<td>Number Of Sections
</td></tr>
<tr>
<td><tt>0x08</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>TimeDateStamp
</td>
<td>The low 32 bits of the number of seconds since 00:00 January 1, 1970 (a C run-time time_t value), that indicates when the file was created.
</td></tr>
<tr>
<td><tt>0x0C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>PointerToSymbolTable
</td>
<td>The file offset of the COFF symbol table, or zero if no COFF symbol table is present. This value should be zero for an image because COFF debugging information is deprecated.
</td></tr>
<tr>
<td><tt>0x10</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>NumberOfSymbols
</td>
<td>The number of entries in the symbol table. This data can be used to locate the string table, which immediately follows the symbol table. This value should be zero for an image because COFF debugging information is deprecated.
</td></tr>
<tr>
<td><tt>0x14</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>SizeOfOptionalHeader
</td>
<td>The size of the optional header, which is required for executable files but not for object files. This value should be zero for an object file.
</td></tr>
<tr>
<td><tt>0x16</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>Characteristics
</td>
<td>The flags that indicate the attributes of the file. For list of values, refer to the <a href="#Image_Characteristics">Image Characteristics section</a>.
</td></tr>
<tr>
<th colspan="4">
<h3><span id="Optional_Header_(0x18)"></span><span class="mw-headline" id="Optional_Header_.280x18.29">Optional Header (<tt>0x18</tt>)</span></h3>
</th></tr>
<tr>
<td><tt>0x18</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>Magic
</td>
<td>The unsigned integer that identifies the state of the image file. The most common number is <tt>0x10B</tt>, which identifies it as a normal executable file (PE32). <tt>0x107</tt> identifies it as a ROM image, and <tt>0x20B</tt> identifies it as a PE32+ executable.
</td></tr>
<tr>
<td><tt>0x1A</tt>
</td>
<td><tt>BYTE</tt>
</td>
<td>MajorLinkerVersion
</td>
<td>The linker major version number.
</td></tr>
<tr>
<td><tt>0x1B</tt>
</td>
<td><tt>BYTE</tt>
</td>
<td>MinorLinkerVersion
</td>
<td>The linker minor version number.
</td></tr>
<tr>
<td><tt>0x1C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SizeOfCode
</td>
<td>The size of the code (text) section, or the sum of all code sections if there are multiple sections.
</td></tr>
<tr>
<td><tt>0x20</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SizeOfInitializedData
</td>
<td>The size of the initialized data section, or the sum of all such sections if there are multiple data sections.
</td></tr>
<tr>
<td><tt>0x24</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SizeOfUninitializedData
</td>
<td>The size of the uninitialized data section (BSS), or the sum of all such sections if there are multiple BSS sections.
</td></tr>
<tr>
<td><tt>0x28</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>AddressOfEntryPoint
</td>
<td>The address of the entry point relative to the image base when the executable file is loaded into memory. For program images, this is the starting address. For device drivers, this is the address of the initialization function. An entry point is optional for DLLs. When no entry point is present, this field must be zero.
</td></tr>
<tr>
<td><tt>0x2C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>BaseOfCode
</td>
<td>The address that is relative to the image base of the beginning-of-code section when it is loaded into memory.
</td></tr>
<tr>
<td><tt>0x30</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>BaseOfData
</td>
<td>This field does not appear in PE32+. The address that is relative to the image base of the beginning-of-data section when it is loaded into memory.
</td></tr>
<tr>
<td><tt>0x34</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>ImageBase
</td>
<td>The preferred address of the first byte of image when loaded into memory; must be a multiple of 64&nbsp;K. The default for DLLs is <tt>0x10000000</tt>. The default for Windows CE EXEs is <tt>0x00010000</tt>. The default for Windows&nbsp;NT, Windows 2000, Windows&nbsp;XP, Windows&nbsp;95, Windows&nbsp;98, and Windows&nbsp;Me is <tt>0x00400000</tt>.
</td></tr>
<tr>
<td><tt>0x38</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SectionAlignment
</td>
<td>The alignment (in bytes) of sections when they are loaded into memory. It must be greater than or equal to <i>FileAlignment</i>. The default is the page size for the architecture.
</td></tr>
<tr>
<td><tt>0x3C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>FileAlignment
</td>
<td>The alignment factor (in bytes) that is used to align the raw data of sections in the image file. The value should be a power of 2 between 512 and 64&nbsp;K, inclusive. The default is 512. If the <i>SectionAlignment</i> is less than the architecture's page size, then <i>FileAlignment</i> must match <i>SectionAlignment</i>.
</td></tr>
<tr>
<td><tt>0x40</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>MajorOperatingSystemVersion
</td>
<td>The major version number of the required operating system.
</td></tr>
<tr>
<td><tt>0x42</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>MinorOperatingSystemVersion
</td>
<td>The minor version number of the required operating system.
</td></tr>
<tr>
<td><tt>0x44</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>MajorImageVersion
</td>
<td>The major version number of the image.
</td></tr>
<tr>
<td><tt>0x46</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>MinorImageVersion
</td>
<td>The minor version number of the image.
</td></tr>
<tr>
<td><tt>0x48</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>MajorSubsystemVersion
</td>
<td>The major version number of the subsystem.
</td></tr>
<tr>
<td><tt>0x4A</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>MinorSubsystemVersion
</td>
<td>The minor version number of the subsystem.
</td></tr>
<tr>
<td><tt>0x4C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Win32VersionValue
</td>
<td>Reserved, must be zero.
</td></tr>
<tr>
<td><tt>0x50</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SizeOfImage
</td>
<td>The size (in bytes) of the image, including all headers, as the image is loaded in memory. It must be a multiple of SectionAlignment.
</td></tr>
<tr>
<td><tt>0x54</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SizeOfHeaders
</td>
<td>The combined size of an MS‑DOS stub, PE header, and section headers rounded up to a multiple of FileAlignment.
</td></tr>
<tr>
<td><tt>0x58</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>CheckSum
</td>
<td>The image file checksum. The algorithm for computing the checksum is incorporated into <tt><b>IMAGHELP.DLL</b></tt>. The following are checked for validation at load time: all drivers, any DLL loaded at boot time, and any DLL that is loaded into a critical Windows process.
</td></tr>
<tr>
<td><tt>0x5C</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>Subsystem
</td>
<td>The subsystem that is required to run this image. For list of values, refer to the <a href="#Windows_Subsystem">Windows Subsystem section</a>.
</td></tr>
<tr>
<td><tt>0x5E</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>DllCharacteristics
</td>
<td>For list of values, refer to the <a href="#DLL_Characteristics">DLL Characteristics section</a>.
</td></tr>
<tr>
<td><tt>0x60</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SizeOfStackReserve
</td>
<td>The size of the stack to reserve. Only <i>SizeOfStackCommit</i> is committed; the rest is made available one page at a time until the reserve size is reached.
</td></tr>
<tr>
<td><tt>0x64</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SizeOfStackCommit
</td>
<td>The size of the stack to commit.
</td></tr>
<tr>
<td><tt>0x68</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SizeOfHeapReserve
</td>
<td>The size of the local heap space to reserve. Only SizeOfHeapCommit is committed; the rest is made available one page at a time until the reserve size is reached.
</td></tr>
<tr>
<td><tt>0x6C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SizeOfHeapCommit
</td>
<td>The size of the local heap space to commit.
</td></tr>
<tr>
<td><tt>0x70</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>LoaderFlags
</td>
<td>Reserved, must be zero.
</td></tr>
<tr>
<td><tt>0x74</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>NumberOfRvaAndSizes
</td>
<td>
<p>The number of data-directory entries in the remainder of the optional header. Each describes a location and size.
</p>
<div style="margin:5px; padding:5px; border-left: solid 10px #90C3D4; background:#E9F2F5;">
<div class="floatleft"><a href="/wiki/File:Info.png" class="image"><img alt="Info.png" src="/w/images/b/b3/Info.png" decoding="async" width="34" height="34"></a></div>
<div style="margin:3px;font-weight:bold;">Note</div>
<div>Malware can set an invalid value for this flag to crash the debugger. <a href="/wiki/Invalid-NumberOfRvaAndSizes" title="Invalid-NumberOfRvaAndSizes">Read more</a>.</div>
</div>
</td></tr>
<tr>
<th colspan="4">
<h3><span id="Data_Directories_(0x78)"></span><span class="mw-headline" id="Data_Directories_.280x78.29">Data Directories (<tt>0x78</tt>)</span></h3>
</th></tr>
<tr valign="top">
<td><tt>0x78</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td><a href="#Export_Table">Export Table</a>
</td>
<td>RVA of Export Directory
</td></tr>
<tr>
<td><tt>0x7C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Export Directory
</td></tr>
<tr>
<td><tt>0x80</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td><a href="#Import_Table">Import Table</a>
</td>
<td>RVA of Import Directory (array of IIDs)
</td></tr>
<tr>
<td><tt>0x84</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Import Directory (array of IIDs)
</td></tr>
<tr>
<td><tt>0x88</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Resource Table
</td>
<td>RVA of Resource Directory
</td></tr>
<tr>
<td><tt>0x8C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Resource Directory
</td></tr>
<tr>
<td><tt>0x90</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Exception Table
</td>
<td>RVA of Exception Directory
</td></tr>
<tr>
<td><tt>0x94</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Exception Directory
</td></tr>
<tr>
<td><tt>0x98</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Certificate Table
</td>
<td>Raw Offset of Security Directory
</td></tr>
<tr>
<td><tt>0x9C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Security Directory
</td></tr>
<tr>
<td><tt>0xA0</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Base Relocation Table
</td>
<td>RVA of Base Relocation Directory
</td></tr>
<tr>
<td><tt>0xA4</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Base Relocation Directory
</td></tr>
<tr>
<td><tt>0xA8</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Debug
</td>
<td>RVA of Debug Directory
</td></tr>
<tr>
<td><tt>0xAC</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Debug Directory
</td></tr>
<tr>
<td><tt>0xB0</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Architecture
</td>
<td>RVA of Copyright Note
</td></tr>
<tr>
<td><tt>0xB4</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Copyright Note
</td></tr>
<tr>
<td><tt>0xB8</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Global Ptr
</td>
<td>RVA to be used as Global Pointer (IA-64 only)
</td></tr>
<tr>
<td><tt>0xBC</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>Not used
</td></tr>
<tr>
<td><tt>0xC0</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>TLS Table
</td>
<td>RVA of Thread Local Storage Directory
</td></tr>
<tr>
<td><tt>0xC4</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Thread Local Storage Directory
</td></tr>
<tr>
<td><tt>0xC8</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Load Config Table
</td>
<td>RVA of Load Configuration Directory
</td></tr>
<tr>
<td><tt>0xCC</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Load Configuration Directory
</td></tr>
<tr>
<td><tt>0xD0</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Bound Import
</td>
<td>RVA of Bound Import Directory
</td></tr>
<tr>
<td><tt>0xD4</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Bound Import Directory
</td></tr>
<tr>
<td><tt>0xD8</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>IAT
</td>
<td>RVA of first Import Address Table
</td></tr>
<tr>
<td><tt>0xDC</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>total size of all Import Address Tables
</td></tr>
<tr>
<td><tt>0xE0</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Delay Import Descriptor
</td>
<td>RVA of Delay Import Directory
</td></tr>
<tr>
<td><tt>0xE4</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of Delay Import Directory
</td></tr>
<tr>
<td><tt>0xE8</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>CLR Runtime Header
</td>
<td>RVA of COM Header (top level info &amp; metadata...)
</td></tr>
<tr>
<td><tt>0xEC</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>
</td>
<td>size of COM Header (in .NET executables)
</td></tr>
<tr>
<td><tt>0xF0</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>ZERO (Reserved)
</td>
<td>Reserved
</td></tr>
<tr>
<td><tt>0xF4</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>ZERO (Reserved)
</td>
<td>Reserved
</td></tr>
<tr>
<th colspan="4">
<h3><span id="Section_Table_(0xF8)"></span><span class="mw-headline" id="Section_Table_.280xF8.29">Section Table (<tt>0xF8</tt>)</span></h3>
</th></tr>
<tr>
<td><tt>0x00</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Name
</td>
<td>An 8-byte, null-padded UTF-8 encoded string. If the string is exactly 8 characters long, there is no terminating null. For longer names, this field contains a slash (/) that is followed by an ASCII representation of a decimal number that is an offset into the string table. Executable images do not use a string table and do not support section names longer than 8 characters. Long names in object files are truncated if they are emitted to an executable file.
</td></tr>
<tr>
<td><tt>0x08</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>VirtualSize
</td>
<td>The total size of the section when loaded into memory. If this value is greater than <i>SizeOfRawData</i>, the section is zero-padded. This field is valid only for executable images and should be set to zero for object files.
</td></tr>
<tr>
<td><tt>0x0C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>VirtualAddress
</td>
<td>For executable images, the address of the first byte of the section relative to the image base when the section is loaded into memory. For object files, this field is the address of the first byte before relocation is applied; for simplicity, compilers should set this to zero. Otherwise, it is an arbitrary value that is subtracted from offsets during relocation.
</td></tr>
<tr>
<td><tt>0x10</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>SizeOfRawData
</td>
<td>
<p>The size of the section (for object files) or the size of the initialized data on disk (for image files). For executable images, this must be a multiple of <i>FileAlignment</i> from the optional header. If this is less than <i>VirtualSize</i>, the remainder of the section is zero-filled. Because the <i>SizeOfRawData</i> field is rounded but the <i>VirtualSize</i> field is not, it is possible for <i>SizeOfRawData</i> to be greater than <i>VirtualSize</i> as well. When a section contains only uninitialized data, this field should be zero.
</p>
<div style="margin:5px; padding:5px; border-left: solid 10px #90C3D4; background:#E9F2F5;">
<div class="floatleft"><a href="/wiki/File:Info.png" class="image"><img alt="Info.png" src="/w/images/b/b3/Info.png" decoding="async" width="34" height="34"></a></div>
<div style="margin:3px;font-weight:bold;">Note</div>
<div>Malware can set an invalid value for this flag to crash the debugger. <a href="/wiki/Invalid-SizeOfRawData" title="Invalid-SizeOfRawData">Read more</a>.</div>
</div>
</td></tr>
<tr>
<td><tt>0x14</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>PointerToRawData
</td>
<td>The file pointer to the first page of the section within the COFF file. For executable images, this must be a multiple of <i>FileAlignment</i> from the optional header. For object files, the value should be aligned on a 4‑byte boundary for best performance. When a section contains only uninitialized data, this field should be zero.
</td></tr>
<tr>
<td><tt>0x18</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>PointerToRelocations
</td>
<td>The file pointer to the beginning of relocation entries for the section. This is set to zero for executable images or if there are no relocations.
</td></tr>
<tr>
<td><tt>0x1C</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>PointerToLinenumbers
</td>
<td>The file pointer to the beginning of line-number entries for the section. This is set to zero if there are no COFF line numbers. This value should be zero for an image because COFF debugging information is deprecated.
</td></tr>
<tr>
<td><tt>0x20</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>NumberOfRelocations
</td>
<td>The number of relocation entries for the section. This is set to zero for executable images.
</td></tr>
<tr>
<td><tt>0x22</tt>
</td>
<td><tt>WORD</tt>
</td>
<td>NumberOfLineNumbers
</td>
<td>The number of line-number entries for the section. This value should be zero for an image because COFF debugging information is deprecated.
</td></tr>
<tr>
<td><tt>0x24</tt>
</td>
<td><tt>DWORD</tt>
</td>
<td>Characteristics
</td>
<td>The flags that describe the characteristics of the section. See values in the <a href="#Section_Characteristics">Section Characteristics section</a>.
</td></tr>
<tr>
<th colspan="4">Repeats for rest of sections
</th></tr>
<tr>
<td><tt>0x00</tt>
</td>
<td><tt>8 Bytes</tt>
</td>
<td>Name
</td>
<td>Name of second section header
</td></tr>
<tr>
<td>...
</td>
<td>...
</td>
<td>...
</td>
<td>...
</td></tr></tbody>
