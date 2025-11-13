[assignment6.ipynb](https://github.com/user-attachments/files/23518694/assignment6.ipynb)https://datawrapper.dwcdn.net/lrEHs/6/

[Uploading assignment6.{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 2,
   "id": "cf012895-cab9-4ac0-9c54-6bf367bc5514",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Collecting datawrapper\n",
      "  Downloading datawrapper-2.0.13-py3-none-any.whl.metadata (4.9 kB)\n",
      "Requirement already satisfied: importlib_metadata in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from datawrapper) (8.4.0)\n",
      "Collecting rich (from datawrapper)\n",
      "  Downloading rich-14.2.0-py3-none-any.whl.metadata (18 kB)\n",
      "Requirement already satisfied: requests in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from datawrapper) (2.32.3)\n",
      "Requirement already satisfied: pandas in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from datawrapper) (2.2.2)\n",
      "Collecting pydantic (from datawrapper)\n",
      "  Downloading pydantic-2.12.4-py3-none-any.whl.metadata (89 kB)\n",
      "Requirement already satisfied: ipython in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from datawrapper) (8.26.0)\n",
      "Requirement already satisfied: zipp>=0.5 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from importlib_metadata->datawrapper) (3.20.1)\n",
      "Requirement already satisfied: decorator in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from ipython->datawrapper) (5.1.1)\n",
      "Requirement already satisfied: jedi>=0.16 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from ipython->datawrapper) (0.19.1)\n",
      "Requirement already satisfied: matplotlib-inline in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from ipython->datawrapper) (0.1.7)\n",
      "Requirement already satisfied: prompt-toolkit<3.1.0,>=3.0.41 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from ipython->datawrapper) (3.0.47)\n",
      "Requirement already satisfied: pygments>=2.4.0 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from ipython->datawrapper) (2.18.0)\n",
      "Requirement already satisfied: stack-data in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from ipython->datawrapper) (0.6.2)\n",
      "Requirement already satisfied: traitlets>=5.13.0 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from ipython->datawrapper) (5.14.3)\n",
      "Requirement already satisfied: pexpect>4.3 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from ipython->datawrapper) (4.9.0)\n",
      "Requirement already satisfied: numpy>=1.26.0 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from pandas->datawrapper) (2.1.0)\n",
      "Requirement already satisfied: python-dateutil>=2.8.2 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from pandas->datawrapper) (2.9.0)\n",
      "Requirement already satisfied: pytz>=2020.1 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from pandas->datawrapper) (2024.1)\n",
      "Requirement already satisfied: tzdata>=2022.7 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from pandas->datawrapper) (2024.1)\n",
      "Collecting annotated-types>=0.6.0 (from pydantic->datawrapper)\n",
      "  Downloading annotated_types-0.7.0-py3-none-any.whl.metadata (15 kB)\n",
      "Collecting pydantic-core==2.41.5 (from pydantic->datawrapper)\n",
      "  Downloading pydantic_core-2.41.5-cp312-cp312-macosx_10_12_x86_64.whl.metadata (7.3 kB)\n",
      "Collecting typing-extensions>=4.14.1 (from pydantic->datawrapper)\n",
      "  Downloading typing_extensions-4.15.0-py3-none-any.whl.metadata (3.3 kB)\n",
      "Collecting typing-inspection>=0.4.2 (from pydantic->datawrapper)\n",
      "  Downloading typing_inspection-0.4.2-py3-none-any.whl.metadata (2.6 kB)\n",
      "Requirement already satisfied: charset-normalizer<4,>=2 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from requests->datawrapper) (3.3.2)\n",
      "Requirement already satisfied: idna<4,>=2.5 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from requests->datawrapper) (3.8)\n",
      "Requirement already satisfied: urllib3<3,>=1.21.1 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from requests->datawrapper) (2.2.2)\n",
      "Requirement already satisfied: certifi>=2017.4.17 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from requests->datawrapper) (2024.7.4)\n",
      "Collecting markdown-it-py>=2.2.0 (from rich->datawrapper)\n",
      "  Downloading markdown_it_py-4.0.0-py3-none-any.whl.metadata (7.3 kB)\n",
      "Requirement already satisfied: parso<0.9.0,>=0.8.3 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from jedi>=0.16->ipython->datawrapper) (0.8.4)\n",
      "Collecting mdurl~=0.1 (from markdown-it-py>=2.2.0->rich->datawrapper)\n",
      "  Downloading mdurl-0.1.2-py3-none-any.whl.metadata (1.6 kB)\n",
      "Requirement already satisfied: ptyprocess>=0.5 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from pexpect>4.3->ipython->datawrapper) (0.7.0)\n",
      "Requirement already satisfied: wcwidth in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from prompt-toolkit<3.1.0,>=3.0.41->ipython->datawrapper) (0.2.13)\n",
      "Requirement already satisfied: six>=1.5 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from python-dateutil>=2.8.2->pandas->datawrapper) (1.16.0)\n",
      "Requirement already satisfied: executing>=1.2.0 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from stack-data->ipython->datawrapper) (2.0.1)\n",
      "Requirement already satisfied: asttokens>=2.1.0 in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from stack-data->ipython->datawrapper) (2.4.1)\n",
      "Requirement already satisfied: pure-eval in ./Library/jupyterlab-desktop/jlab_server/lib/python3.12/site-packages (from stack-data->ipython->datawrapper) (0.2.3)\n",
      "Downloading datawrapper-2.0.13-py3-none-any.whl (102 kB)\n",
      "Downloading pydantic-2.12.4-py3-none-any.whl (463 kB)\n",
      "Downloading pydantic_core-2.41.5-cp312-cp312-macosx_10_12_x86_64.whl (2.1 MB)\n",
      "\u001b[2K   \u001b[90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━\u001b[0m \u001b[32m2.1/2.1 MB\u001b[0m \u001b[31m6.6 MB/s\u001b[0m eta \u001b[36m0:00:00\u001b[0ma \u001b[36m0:00:01\u001b[0m\n",
      "\u001b[?25hDownloading rich-14.2.0-py3-none-any.whl (243 kB)\n",
      "Downloading annotated_types-0.7.0-py3-none-any.whl (13 kB)\n",
      "Downloading markdown_it_py-4.0.0-py3-none-any.whl (87 kB)\n",
      "Downloading typing_extensions-4.15.0-py3-none-any.whl (44 kB)\n",
      "Downloading typing_inspection-0.4.2-py3-none-any.whl (14 kB)\n",
      "Downloading mdurl-0.1.2-py3-none-any.whl (10.0 kB)\n",
      "Installing collected packages: typing-extensions, mdurl, annotated-types, typing-inspection, pydantic-core, markdown-it-py, rich, pydantic, datawrapper\n",
      "  Attempting uninstall: typing-extensions\n",
      "    Found existing installation: typing_extensions 4.12.2\n",
      "    Uninstalling typing_extensions-4.12.2:\n",
      "      Successfully uninstalled typing_extensions-4.12.2\n",
      "Successfully installed annotated-types-0.7.0 datawrapper-2.0.13 markdown-it-py-4.0.0 mdurl-0.1.2 pydantic-2.12.4 pydantic-core-2.41.5 rich-14.2.0 typing-extensions-4.15.0 typing-inspection-0.4.2\n"
     ]
    }
   ],
   "source": [
    "!pip install datawrapper"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 13,
   "id": "4d096c5e-0c07-48f4-8ed6-90f8c246a9ce",
   "metadata": {},
   "outputs": [],
   "source": [
    "!pip install pandas "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "id": "9c3ff7c9-7582-400b-9f3c-8c46a422dd89",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>RowID</th>\n",
       "      <th>X</th>\n",
       "      <th>Y</th>\n",
       "      <th>IncidentNumber</th>\n",
       "      <th>ArrestNumber</th>\n",
       "      <th>Age</th>\n",
       "      <th>Gender</th>\n",
       "      <th>Race</th>\n",
       "      <th>ArrestDateTime</th>\n",
       "      <th>ArrestLocation</th>\n",
       "      <th>...</th>\n",
       "      <th>ChargeDescription</th>\n",
       "      <th>District</th>\n",
       "      <th>Post</th>\n",
       "      <th>Neighborhood</th>\n",
       "      <th>Latitude</th>\n",
       "      <th>Longitude</th>\n",
       "      <th>GeoLocation</th>\n",
       "      <th>Shape</th>\n",
       "      <th>Year</th>\n",
       "      <th>year</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>29</td>\n",
       "      <td>1.401347e+06</td>\n",
       "      <td>608148.870493</td>\n",
       "      <td>22L09338</td>\n",
       "      <td>23000037.0</td>\n",
       "      <td>39.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:50:00</td>\n",
       "      <td>4000 OAKFORD ST</td>\n",
       "      <td>...</td>\n",
       "      <td>HAND GUN VIOLATION</td>\n",
       "      <td>Northwest</td>\n",
       "      <td>621.0</td>\n",
       "      <td>West Arlington</td>\n",
       "      <td>39.3361</td>\n",
       "      <td>-76.6853</td>\n",
       "      <td>(39.3361,-76.6853)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>30</td>\n",
       "      <td>1.401347e+06</td>\n",
       "      <td>608148.870493</td>\n",
       "      <td>22L09338</td>\n",
       "      <td>23000039.0</td>\n",
       "      <td>50.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:50:00</td>\n",
       "      <td>4000 OAKFORD ST</td>\n",
       "      <td>...</td>\n",
       "      <td>HAND GUN VIOLATION</td>\n",
       "      <td>Northwest</td>\n",
       "      <td>621.0</td>\n",
       "      <td>West Arlington</td>\n",
       "      <td>39.3361</td>\n",
       "      <td>-76.6853</td>\n",
       "      <td>(39.3361,-76.6853)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>31</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>23000010.0</td>\n",
       "      <td>27.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:40:00</td>\n",
       "      <td>NaN</td>\n",
       "      <td>...</td>\n",
       "      <td>FAILURE TO APPEAR</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>(,)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>32</td>\n",
       "      <td>1.417636e+06</td>\n",
       "      <td>595206.835862</td>\n",
       "      <td>22L09343</td>\n",
       "      <td>23000050.0</td>\n",
       "      <td>42.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:15:00</td>\n",
       "      <td>500 DOLPHIN ST</td>\n",
       "      <td>...</td>\n",
       "      <td>HAND GUN VIOLATION</td>\n",
       "      <td>Central</td>\n",
       "      <td>123.0</td>\n",
       "      <td>Upton</td>\n",
       "      <td>39.3004</td>\n",
       "      <td>-76.6279</td>\n",
       "      <td>(39.3004,-76.6279)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>33</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>22L09312</td>\n",
       "      <td>22157183.0</td>\n",
       "      <td>43.0</td>\n",
       "      <td>F</td>\n",
       "      <td>W</td>\n",
       "      <td>2022-12-31 21:00:00</td>\n",
       "      <td>1500 BECKLOW AVE</td>\n",
       "      <td>...</td>\n",
       "      <td>STOLEN AUTO</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>(,)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>5 rows × 23 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "   RowID             X              Y IncidentNumber  ArrestNumber   Age  \\\n",
       "0     29  1.401347e+06  608148.870493       22L09338    23000037.0  39.0   \n",
       "1     30  1.401347e+06  608148.870493       22L09338    23000039.0  50.0   \n",
       "2     31           NaN            NaN            NaN    23000010.0  27.0   \n",
       "3     32  1.417636e+06  595206.835862       22L09343    23000050.0  42.0   \n",
       "4     33           NaN            NaN       22L09312    22157183.0  43.0   \n",
       "\n",
       "  Gender Race      ArrestDateTime    ArrestLocation  ...   ChargeDescription  \\\n",
       "0      M    B 2022-12-31 23:50:00   4000 OAKFORD ST  ...  HAND GUN VIOLATION   \n",
       "1      M    B 2022-12-31 23:50:00   4000 OAKFORD ST  ...  HAND GUN VIOLATION   \n",
       "2      M    B 2022-12-31 23:40:00               NaN  ...   FAILURE TO APPEAR   \n",
       "3      M    B 2022-12-31 23:15:00    500 DOLPHIN ST  ...  HAND GUN VIOLATION   \n",
       "4      F    W 2022-12-31 21:00:00  1500 BECKLOW AVE  ...         STOLEN AUTO   \n",
       "\n",
       "    District   Post    Neighborhood Latitude  Longitude         GeoLocation  \\\n",
       "0  Northwest  621.0  West Arlington  39.3361   -76.6853  (39.3361,-76.6853)   \n",
       "1  Northwest  621.0  West Arlington  39.3361   -76.6853  (39.3361,-76.6853)   \n",
       "2        NaN    NaN             NaN      NaN        NaN                 (,)   \n",
       "3    Central  123.0           Upton  39.3004   -76.6279  (39.3004,-76.6279)   \n",
       "4        NaN    NaN             NaN      NaN        NaN                 (,)   \n",
       "\n",
       "   Shape  Year  year  \n",
       "0    NaN  2022  2022  \n",
       "1    NaN  2022  2022  \n",
       "2    NaN  2022  2022  \n",
       "3    NaN  2022  2022  \n",
       "4    NaN  2022  2022  \n",
       "\n",
       "[5 rows x 23 columns]"
      ]
     },
     "execution_count": 16,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df = pd.read_csv(\n",
    "    \"https://raw.githubusercontent.com/palewire/first-automated-chart/main/_notebooks/arrests.csv\",\n",
    "    parse_dates=[\"ArrestDateTime\"]\n",
    ")\n",
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 17,
   "id": "9961deca-2c67-47a2-9438-c6c783b83e28",
   "metadata": {},
   "outputs": [],
   "source": [
    "df['year'] = df.ArrestDateTime.dt.year"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 18,
   "id": "3d349aaf-d03c-4b19-a684-c338b1d2c857",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "year\n",
       "2010    45224\n",
       "2011    43364\n",
       "2012    42333\n",
       "2013    39542\n",
       "2014    37078\n",
       "2015    25732\n",
       "2016    23089\n",
       "2017    21989\n",
       "2018    20543\n",
       "2019    19407\n",
       "2023    13566\n",
       "2020    13162\n",
       "2022    12360\n",
       "2021    11130\n",
       "Name: count, dtype: int64"
      ]
     },
     "execution_count": 18,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.year.value_counts()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 19,
   "id": "a43e3e2f-eca9-48cb-a20a-cc1ec7fa168a",
   "metadata": {},
   "outputs": [],
   "source": [
    "totals_by_year = df.year.value_counts().sort_index().reset_index()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 20,
   "id": "f59cda0e-377b-40a8-a00e-784f2740e5bf",
   "metadata": {},
   "outputs": [],
   "source": [
    "chart = dw.ColumnChart(\n",
    "    title=\"Baltimore Arrests\",\n",
    "    data=totals_by_year\n",
    ")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 21,
   "id": "9805b37c-2f8c-44b9-b518-97148edc75b5",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='', source_url='', byline='', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='lrEHs', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color=0, negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 21,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.create()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 22,
   "id": "7d4130d5-1af5-4a4f-a81f-cd344b115e2d",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='', source_url='', byline='', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='lrEHs', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color=0, negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 22,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.publish()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 23,
   "id": "b0ab43b7-e7d0-48ac-bb5d-3c6d27d80f1d",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"410\"\n",
       "            src=\"https://datawrapper.dwcdn.net/lrEHs/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x169e8b2c0>"
      ]
     },
     "execution_count": 23,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.display()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 27,
   "id": "54ee3913-b4ff-45cb-9fee-bd8a079a82df",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='OpenBaltimore', source_url='https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about', byline='Alana Brasure', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='lrEHs', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color=0, negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 27,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.source_name = \"OpenBaltimore\"\n",
    "chart.source_url = \"https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about\"\n",
    "chart.byline = \"Alana Brasure\"\n",
    "chart.update()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 25,
   "id": "c255b8fe-96cd-4165-86ca-b442c4c4cda1",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='OpenBaltimore', source_url='https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about', byline='First Automated Chart', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='lrEHs', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color=0, negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 25,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.publish()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 28,
   "id": "ac1fcc31-2148-4a98-bb3c-395e85fd780d",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='OpenBaltimore', source_url='https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about', byline='Alana Brasure', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='lrEHs', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color=0, negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 28,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.source_name = \"OpenBaltimore\"\n",
    "chart.source_url = \"https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about\"\n",
    "chart.byline = \"Alana Brasure\"\n",
    "chart.update()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 29,
   "id": "f3b31f2e-da43-4289-a123-10d6adc10e0e",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='OpenBaltimore', source_url='https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about', byline='Alana Brasure', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='lrEHs', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color=0, negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 29,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.publish()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 30,
   "id": "6f793c62-2f39-4c26-ac7f-e17d8050cc3b",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"410\"\n",
       "            src=\"https://datawrapper.dwcdn.net/lrEHs/3/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x169f16870>"
      ]
     },
     "execution_count": 30,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.display()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 34,
   "id": "103bfb36-ab98-433e-af53-6a2874936bae",
   "metadata": {},
   "outputs": [],
   "source": [
    "chart.base_color = \"#004FA2\"  "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 35,
   "id": "1d104229-3e7f-4cf9-bd88-37acbae18f20",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='OpenBaltimore', source_url='https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about', byline='Alana Brasure', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='lrEHs', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color='#004FA2', negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 35,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.update()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 36,
   "id": "8b07f09b-1c8c-4a2c-9364-d7d2b9347842",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='OpenBaltimore', source_url='https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about', byline='Alana Brasure', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='lrEHs', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color='#004FA2', negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 36,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.publish()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 37,
   "id": "34219f32-36e3-44af-b467-886f1eca28fc",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"410\"\n",
       "            src=\"https://datawrapper.dwcdn.net/lrEHs/5/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x169f15e50>"
      ]
     },
     "execution_count": 37,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.display()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 38,
   "id": "2512d8b8-eb07-40c1-b4cc-e5a710eacefb",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>RowID</th>\n",
       "      <th>X</th>\n",
       "      <th>Y</th>\n",
       "      <th>IncidentNumber</th>\n",
       "      <th>ArrestNumber</th>\n",
       "      <th>Age</th>\n",
       "      <th>Gender</th>\n",
       "      <th>Race</th>\n",
       "      <th>ArrestDateTime</th>\n",
       "      <th>ArrestLocation</th>\n",
       "      <th>...</th>\n",
       "      <th>ChargeDescription</th>\n",
       "      <th>District</th>\n",
       "      <th>Post</th>\n",
       "      <th>Neighborhood</th>\n",
       "      <th>Latitude</th>\n",
       "      <th>Longitude</th>\n",
       "      <th>GeoLocation</th>\n",
       "      <th>Shape</th>\n",
       "      <th>Year</th>\n",
       "      <th>year</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>29</td>\n",
       "      <td>1.401347e+06</td>\n",
       "      <td>608148.870493</td>\n",
       "      <td>22L09338</td>\n",
       "      <td>23000037.0</td>\n",
       "      <td>39.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:50:00</td>\n",
       "      <td>4000 OAKFORD ST</td>\n",
       "      <td>...</td>\n",
       "      <td>HAND GUN VIOLATION</td>\n",
       "      <td>Northwest</td>\n",
       "      <td>621.0</td>\n",
       "      <td>West Arlington</td>\n",
       "      <td>39.3361</td>\n",
       "      <td>-76.6853</td>\n",
       "      <td>(39.3361,-76.6853)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>30</td>\n",
       "      <td>1.401347e+06</td>\n",
       "      <td>608148.870493</td>\n",
       "      <td>22L09338</td>\n",
       "      <td>23000039.0</td>\n",
       "      <td>50.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:50:00</td>\n",
       "      <td>4000 OAKFORD ST</td>\n",
       "      <td>...</td>\n",
       "      <td>HAND GUN VIOLATION</td>\n",
       "      <td>Northwest</td>\n",
       "      <td>621.0</td>\n",
       "      <td>West Arlington</td>\n",
       "      <td>39.3361</td>\n",
       "      <td>-76.6853</td>\n",
       "      <td>(39.3361,-76.6853)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>31</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>23000010.0</td>\n",
       "      <td>27.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:40:00</td>\n",
       "      <td>NaN</td>\n",
       "      <td>...</td>\n",
       "      <td>FAILURE TO APPEAR</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>(,)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>32</td>\n",
       "      <td>1.417636e+06</td>\n",
       "      <td>595206.835862</td>\n",
       "      <td>22L09343</td>\n",
       "      <td>23000050.0</td>\n",
       "      <td>42.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:15:00</td>\n",
       "      <td>500 DOLPHIN ST</td>\n",
       "      <td>...</td>\n",
       "      <td>HAND GUN VIOLATION</td>\n",
       "      <td>Central</td>\n",
       "      <td>123.0</td>\n",
       "      <td>Upton</td>\n",
       "      <td>39.3004</td>\n",
       "      <td>-76.6279</td>\n",
       "      <td>(39.3004,-76.6279)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>33</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>22L09312</td>\n",
       "      <td>22157183.0</td>\n",
       "      <td>43.0</td>\n",
       "      <td>F</td>\n",
       "      <td>W</td>\n",
       "      <td>2022-12-31 21:00:00</td>\n",
       "      <td>1500 BECKLOW AVE</td>\n",
       "      <td>...</td>\n",
       "      <td>STOLEN AUTO</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>(,)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>5 rows × 23 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "   RowID             X              Y IncidentNumber  ArrestNumber   Age  \\\n",
       "0     29  1.401347e+06  608148.870493       22L09338    23000037.0  39.0   \n",
       "1     30  1.401347e+06  608148.870493       22L09338    23000039.0  50.0   \n",
       "2     31           NaN            NaN            NaN    23000010.0  27.0   \n",
       "3     32  1.417636e+06  595206.835862       22L09343    23000050.0  42.0   \n",
       "4     33           NaN            NaN       22L09312    22157183.0  43.0   \n",
       "\n",
       "  Gender Race      ArrestDateTime    ArrestLocation  ...   ChargeDescription  \\\n",
       "0      M    B 2022-12-31 23:50:00   4000 OAKFORD ST  ...  HAND GUN VIOLATION   \n",
       "1      M    B 2022-12-31 23:50:00   4000 OAKFORD ST  ...  HAND GUN VIOLATION   \n",
       "2      M    B 2022-12-31 23:40:00               NaN  ...   FAILURE TO APPEAR   \n",
       "3      M    B 2022-12-31 23:15:00    500 DOLPHIN ST  ...  HAND GUN VIOLATION   \n",
       "4      F    W 2022-12-31 21:00:00  1500 BECKLOW AVE  ...         STOLEN AUTO   \n",
       "\n",
       "    District   Post    Neighborhood Latitude  Longitude         GeoLocation  \\\n",
       "0  Northwest  621.0  West Arlington  39.3361   -76.6853  (39.3361,-76.6853)   \n",
       "1  Northwest  621.0  West Arlington  39.3361   -76.6853  (39.3361,-76.6853)   \n",
       "2        NaN    NaN             NaN      NaN        NaN                 (,)   \n",
       "3    Central  123.0           Upton  39.3004   -76.6279  (39.3004,-76.6279)   \n",
       "4        NaN    NaN             NaN      NaN        NaN                 (,)   \n",
       "\n",
       "   Shape  Year  year  \n",
       "0    NaN  2022  2022  \n",
       "1    NaN  2022  2022  \n",
       "2    NaN  2022  2022  \n",
       "3    NaN  2022  2022  \n",
       "4    NaN  2022  2022  \n",
       "\n",
       "[5 rows x 23 columns]"
      ]
     },
     "execution_count": 38,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 39,
   "id": "fabc6c52-5157-488d-81e3-496ec67e4277",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "District\n",
       "Western      29842\n",
       "Central      28501\n",
       "Eastern      28114\n",
       "Southern     25780\n",
       "Northeast    24180\n",
       "Southeast    23710\n",
       "Northwest    22044\n",
       "Southwest    21822\n",
       "Northern     13087\n",
       "Name: count, dtype: int64"
      ]
     },
     "execution_count": 39,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.District.value_counts()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 40,
   "id": "42e27c3b-ddbb-46e9-8b58-d984eceb3761",
   "metadata": {},
   "outputs": [],
   "source": [
    "def create_chart(district: str) -> str:\n",
    "    \"\"\"Create a Datawrapper column chart of arrests by year in a Baltimore police district.\n",
    "    \n",
    "    Args:\n",
    "        district: The name of the district to chart.\n",
    "\n",
    "    Returns:\n",
    "        The chart's embed code.\n",
    "    \"\"\"\n",
    "    # Filter the dataframe to the provided district\n",
    "    district_df = df[df.District == district]\n",
    "\n",
    "    # Count the number of arrests in each year\n",
    "    district_by_year = district_df.year.value_counts().sort_index().reset_index()\n",
    "\n",
    "    # Create the chart with Datawrapper\n",
    "    chart = dw.ColumnChart(\n",
    "        # Use the district name in the title\n",
    "        title=f\"Arrests in Baltimore's {district} District\",\n",
    "        # Pass in the filtered data\n",
    "        data=district_by_year,\n",
    "        base_color=\"#bf7836\",\n",
    "        source_name=\"OpenBaltimore\",\n",
    "        source_url=\"https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about\",\n",
    "        byline=\"First Automated Chart\",\n",
    "    )\n",
    "    \n",
    "    # Create the chart\n",
    "    chart.create()\n",
    "\n",
    "    # Publish the chart\n",
    "    chart.publish()\n",
    "\n",
    "    # Return the chart's embed code\n",
    "    return chart.display()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 41,
   "id": "6f536742-15e9-4ce1-8c66-024131299752",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/F3G0K/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x169e8b9e0>"
      ]
     },
     "execution_count": 41,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "create_chart(\"Western\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 42,
   "id": "07b139d3-2d1c-46ab-adaf-2473291b9d3c",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/0WhWl/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x169f15d60>"
      ]
     },
     "execution_count": 42,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "create_chart(\"Eastern\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 43,
   "id": "8f466aaa-a10b-4d4a-ad89-55f16075072f",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Creating chart for the Northwest District\n",
      "Creating chart for the Central District\n",
      "Creating chart for the Western District\n",
      "Creating chart for the Eastern District\n",
      "Creating chart for the Northeast District\n",
      "Creating chart for the Southern District\n",
      "Creating chart for the Southeast District\n",
      "Creating chart for the Northern District\n",
      "Creating chart for the Southwest District\n"
     ]
    }
   ],
   "source": [
    "# Create an empty list to hold the charts\n",
    "chart_list = []\n",
    "\n",
    "# Loop through the unique districts...\n",
    "for district in df.District.dropna().unique():\n",
    "    # Print a message to the console\n",
    "    print(f\"Creating chart for the {district} District\")\n",
    "\n",
    "    # Create a chart for the district and save it as a variable\n",
    "    c = create_chart(district)\n",
    "\n",
    "    # Add the chart to the list\n",
    "    chart_list.append(c)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 44,
   "id": "3ceff7b9-ccde-4533-a0da-28fa2420e468",
   "metadata": {},
   "outputs": [],
   "source": [
    "from IPython.display import display"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 45,
   "id": "e049aab8-998c-4ed9-bc7a-42c1f95d9655",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/rIdDb/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x16d1bd8b0>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/fPHvp/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x16d1beff0>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/X9xVR/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x16d1bea80>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/Wwsoj/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x169f169c0>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/cSgQN/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x16d1bd7c0>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/Q8Tpy/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x169f14e60>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/qSqFX/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x169f15880>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/Q3rV5/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x169f14e90>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/zVhFQ/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x16d1bdb20>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "display(*chart_list)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "1054f2df-07bd-43e0-a4ab-a9e0e94fed71",
   "metadata": {},
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "a33789c2-b4b5-4d21-b358-5eb72d0873fe",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.12.5"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
ipynb…]()
