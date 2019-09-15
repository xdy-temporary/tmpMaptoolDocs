===================================
getEnvironmentVariable - MapToolDoc
===================================

.. contents::
   :depth: 3
..

.. container:: noprint
   :name: mw-page-base

.. container:: noprint
   :name: mw-head-base

.. container:: mw-body
   :name: content

   .. container:: mw-indicators

   .. rubric:: getEnvironmentVariable
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. rubric:: getEnvironmentVariable() Function
            :name: getenvironmentvariable-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Retrieves an operating system environment variable as a
            string.
            This function is useful for situations where the script may
            wish to interact with the environment outside of MapTool,
            such as using the
            `exportData() <exportData>`__ function to
            write a string to an external file.

            .. container:: template_caution

               | **Caution:**
               | This function is considered experimental and its
                 implementation and parameters may change.

            The **Allow External Macro Access** option on the
            Application tab of MapTool's Preferences must be enabled or
            this macro aborts with an error.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getEnvironmentVariable(varname)

         The value of ``varname`` specifies which environment variable
         is queried. On most operating systems, environment variables
         are all uppercase letters, but this is a naming convention and
         not required. Note that no way exists to query what all of the
         environment variables are, so the script writer must know which
         variable they want to retrieve.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            You can use the following code to print the value of the
            PATH environment variable (which exists on most systems).
            Knowing the list of directories where an operating system
            searches for compiled executables could be considered a
            security vulnerability. See the above note about the **Allow
            External Macro Access** option.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [getEnvironmentVariable("PATH")]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getEnvironmentVariable&oldid=7084"

